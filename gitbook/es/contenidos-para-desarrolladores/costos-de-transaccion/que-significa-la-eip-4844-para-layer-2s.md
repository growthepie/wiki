# 🖼️ Qué significa la EIP 4844 para Layer 2s

Al igual que se discutió en Onchain Data Availability en el contexto de las opciones de Disponibilidad de Datos, la EIP 4844 introduce un nuevo formato de transacción, las "transacciones portadoras de blobs", diseñadas para recortar drásticamente las tarifas de gas :fuelpump: y mejorar la escalabilidad.

## **¿Qué son los Blobs?**

1. **Definición**: Los BLOB (Binary Large OBjects) son grandes paquetes de datos separados de los datos de transacción tradicionales de Ethereum. Tienen un formato específico y están pensados para su uso en soluciones de escalado, en particular soluciones de Layer 2 como los Rollups.
2. **Propósito**: Los Blobs se utilizan para almacenar grandes cantidades de datos que no necesitan ser procesados por la Máquina Virtual de Ethereum (EVM), pero que deben estar disponibles para su verificación o uso futuro. Esto es especialmente importante para los Rollups, que procesan transacciones fuera del _chain_ pero requieren la disponibilidad de los datos en la cadena por seguridad y finalidad.
3. **Contenido y formato**: Un blob no se aloja en la capa de ejecución, sino en la capa de consenso del beacon chain. Esta disposición se deriva del hecho de que los blobs no necesitan interactuar de forma nativa con las transacciones, sino que simplemente requieren almacenamiento. Inicialmente se permitirán hasta 16 blobs por bloque de Ethereum, lo que se traduce en un aumento máximo de almacenamiento de 2 MB por bloque (4096 \* 32 bytes \* 16 por bloque). Suponiendo una subasta a precio constante, esto se traduciría en un aumento aproximado de 0,75 MB de disponibilidad de almacenamiento. Por tanto, esta actualización aumentará la capacidad de almacenamiento de Ethereum en un 40% respecto al tamaño máximo teórico de un bloque en la actualidad (30M de gas dividido entre 16 gas por byte = 1,875MB).

### **¿De dónde vienen los blobs?**

1. **Origen**: Los blobs no se derivan de los datos de los bloques actuales o anteriores en el sentido tradicional. En su lugar, se crean como parte de transacciones específicas, conocidas como transacciones portadoras de blobs. Estas transacciones están diseñadas para incluir estos grandes paquetes de datos.
2. **Caso de uso**: Una fuente habitual de blobs son las redes de Layer 2 o Rollups. Estas redes procesan transacciones fuera de la cadena para reducir la carga del chain principal de Ethereum. Los datos resultantes, que deben estar disponibles en la cadena por motivos de seguridad y validación, se empaquetan en blobs.

### **¿En qué se diferencian los blobs de los datos de transacciones normales?**

1. **Almacenamiento y Procesamiento**: A diferencia de los datos de transacciones normales, que son procesados y almacenados por todos los nodos, los blobs están pensados para ser almacenados temporalmente y no son procesados por el EVM. Esto reduce la carga computacional de la red.
2. **Accesibilidad**: El contenido del blob no es directamente accesible en el entorno de ejecución. En su lugar, la transacción que transporta la nota incluye compromisos con las notas. Estos compromisos están disponibles en el entorno de ejecución, mientras que los datos reales se comparten y validan de forma diferente.
3. **Naturaleza temporal**: En algunas propuestas, los blobs se almacenan en la red Ethereum sólo durante un periodo limitado (por ejemplo, unos días o semanas). Tras este periodo, los datos pueden ser eliminados para liberar espacio, ya que su disponibilidad inmediata ya no es crítica.

## **Explicación de la EIP 1559**

El EIP 1559, introducido en Ethereum en 2021, revisó el mecanismo de comisiones por transacción de la red. He aquí un desglose de sus principales características:

1. **Cargo base y propina**: Cada transacción incluye ahora una tarifa base, que se quema (se retira de la circulación), y una propina, o tarifa prioritaria, que se paga a los mineros por un procesamiento más rápido.
2. **Tasa base dinámica**: La tarifa base se ajusta dinámicamente por bloque, aumentando cuando la red está congestionada (más del 50% llena) y disminuyendo cuando está menos utilizada.
3. **Experiencia del usuario**: Los usuarios pueden estimar mejor las tarifas, ya que la tarifa base se determina algorítmicamente en función de la demanda del bloque anterior, mejorando la previsibilidad.

### **Mercado de Tarifas Blobs**

Ahora, integrando este entendimiento con el Mercado de Cuotas Blobs:

1. **Mercado de tarifas separado para Blobs**: Al igual que la EIP 1559 establece una tarifa base dinámica para las transacciones normales, el Mercado de Tarifas de Blobs establece un mecanismo de precios separado para las transacciones que transportan blobs. Esto garantiza que las transacciones de grandes paquetes de datos no afecten ni se vean afectadas por las tarifas de las transacciones regulares.
2. **Tasa Dinámica de Blob**: Similar a la tarifa base del EIP 1559, la tarifa blob se ajusta en función de la demanda de la red, pero independientemente de las tarifas de las transacciones regulares.
3. **Tarifa Máxima por Gas Blob**: Los usuarios especifican la tarifa máxima que están dispuestos a pagar por unidad de gas blob, similar a la propina del EIP 1559. Esto garantiza que su transacción se procesará si la tarifa establecida está por encima de la tarifa blob actual.

## **Escenario**

Consideremos una analogía del mundo real para simplificar esto:

* **EIP 1559 (Transacciones regulares)**: Imagina una autopista con un sistema de peaje dinámico. Cuando la autopista está congestionada, el peaje aumenta para reducir el tráfico y viceversa. Cada coche (transacción) paga un peaje base (tarifa base) que se utiliza para el mantenimiento de la autopista (quemado) y puede pagar un extra (propina) por los carriles prioritarios.
* **Mercado de tarifas de globos (grandes paquetes de datos)**: Ahora, considera un conjunto separado de carriles en esta autopista específicos para camiones que transportan cargas pesadas (transacciones de transporte de blobs). Estos carriles tienen su propio sistema de peaje, independiente de los carriles para coches. El peaje para camiones se ajusta en función de lo ocupados que estén estos carriles, garantizando que el tráfico de camiones no interfiera con el de coches y viceversa.
* **Aplicación en Ethereum**: En Ethereum coexisten las transacciones normales (coches) y las transacciones de grandes paquetes de datos (camiones). Al tener mecanismos de tarificación separados, ambos pueden funcionar eficientemente sin saturar la red, garantizando un flujo más fluido tanto de las transacciones regulares como de las operaciones de datos a gran escala.

## **Layer 2 Rollups post-EIP4844**.

1. **Transacciones portadoras de blobs**:
   * Los Rollups de Layer 2 empaquetarán sus datos en blobs.
   * Estos blobs se incluirán en transacciones portadoras de blobs en la red principal de Ethereum.
   * Este proceso garantiza la disponibilidad de los datos sin necesidad de procesarlos o almacenarlos permanentemente en la Layer 1.
2. **Disponibilidad de datos sin carga**:
   * Los blobs garantizan que los datos necesarios para las transacciones de Rollups estén disponibles en la red principal de Ethereum durante un cierto tiempo.
   * Sin embargo, como estos blobs no son procesados por la Máquina Virtual de Ethereum (EVM), no añaden carga computacional a la red principal.
3. **Almacenamiento temporal**:
   * Los blobs se almacenan en la red Ethereum durante un tiempo limitado (por ejemplo, varios días o semanas).
   * Después de este periodo, los datos pueden ser eliminados, ya que su disponibilidad inmediata ya no es crítica para la seguridad y el funcionamiento de los Rollups.
4. **Seguridad y verificación**:
   * Aunque los datos de los blobs no son procesados por la EVM, siguen siendo esenciales para verificar la corrección de las transacciones de los Rollups.
   * La disponibilidad de estos datos en la red principal significa que cualquier usuario o contrato inteligente puede verificar las transacciones de los Rollups si es necesario.
5. **Eficiencia de costos**:
   * La EIP4844 pretende que el costo del almacenamiento de datos sea más predecible y eficiente para las soluciones de Layer 2.
   * Al separar el mercado de tarifas de los datos blob de las tarifas de las transacciones normales, los Rollups de Layer 2 pueden operar con mayor seguridad de costos.
