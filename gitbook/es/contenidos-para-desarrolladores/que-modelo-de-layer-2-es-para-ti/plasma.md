# ⚡ Plasma

## Escenario 🌟

**Imagina un **_**marketplace**_** de arte digital, donde artistas y coleccionistas compran, venden e intercambian obras de arte digitales únicas. En este mercado, la tecnología Plasma se utiliza para gestionar las transacciones de forma eficaz y segura.**

**Depósito de obras de arte**

1. **Presentación de artistas** 🎨: Una artista, llamémosla Eva, crea una obra de arte digital y decide venderla en el mercado. Deposita su obra de arte en el _smart contract_ del mercado, que es gestionado por Plasma chain.
2. **Identificación Única** 🔢: El _smart contract_ asigna a la obra de arte de Eva un ID único, digamos 537, garantizando que sea distinta y rastreable dentro del Plasma chain.

**Funcionamiento de la cadena de plasma:**

1. **Operador de la cadena** 🔗: El mercado tiene un operador designado para el Plasma chain. Puede ser una entidad centralizada, un grupo que opere bajo multisig o un sistema descentralizado como Proof of Stake (PoS).
2. **Creación de lotes** ⏲️: Cada 15 minutos, el operador reúne todas las transacciones realizadas _off-chain_ en Plasma. Estas transacciones incluyen ventas, compras e intercambios de obras de arte digitales.
3. **Generación del Árbol de Merkle** 🌳: El operador genera un árbol de Merkle a partir de estas transacciones. En este árbol, cada índice corresponde a una transacción relativa a un ID de obra de arte concreto. Si no existe ninguna transacción para una obra de arte, esa parte del árbol permanece vacía.
4. **Publicación y notificación** 📢: El operador publica la raíz Merkle de este árbol en el _chain_ principal de Ethereum. También envía la rama de Merkle correspondiente a cada obra de arte al propietario actual, asegurándose de que tiene la prueba de propiedad (_proof of ownership_).

**Obras de arte en retirada:**

1. **Retirada del Coleccionista** 💼: Un coleccionista, llamémosle Ben, que ha comprado recientemente la obra de arte de Eva (ID 537), decide retirarla del Plasma chain a su _wallet_ privada.
2. **Iniciar la retirada** 🚀: Ben publica la rama Merkle que muestra la transacción más reciente en la que recibió la obra de arte de Eva.
3. **Periodo de Desafío** ⏳: El _smart contrac_t inicia un periodo de desafío de 7 días. Durante este tiempo, otros pueden presentar pruebas utilizando otras ramas de Merkle para demostrar que Eva no era la propietaria de la obra de arte cuando la vendió o que la vendió a otra persona después de Ben.
4. **Retirada con éxito** 🏆: Si nadie impugna con éxito la reclamación de Ben en un plazo de 7 días, se le permite retirar la obra de arte, transfiriéndola de forma segura a su _wallet_ privado.

## Ventajas y Desventajas :arrow\_up::arrow\_down:

### **ventajas**

1. **Accesibilidad más amplia**🌐: Plasma permite enviar activos a participantes que originalmente no formaban parte del sistema, ampliando su alcance más allá de los usuarios iniciales.
2. **Menos requisitos de capital** 💰: A diferencia de los state channels, Plasma requiere un capital significativamente menor para ser bloqueado, lo que lo hace más accesible para operaciones a menor escala.
3. **Alto rendimiento de las transacciones** 🚀: Plasma destaca en el manejo de un gran volumen de transacciones, lo que lo hace ideal para aplicaciones con grandes demandas transaccionales.
4. **Personalización para Casos de Uso Específicos** 🔧: Los Plasma chains pueden adaptarse para satisfacer las necesidades de aplicaciones específicas, ofreciendo flexibilidad en su despliegue.

### Desventajas

1. **Publicación regular de datos en la cadena 📊**: Los avances en las pruebas de validez, como las ZK-SNARK, pueden mitigar la frecuencia y el volumen de publicación de datos _on-chain_ que requiere Plasma, en comparación con sus versiones anteriores.
2. **Retiros retardados ⏳**: El periodo de impugnación en Plasma es necesario para evitar el fraude, pero los nuevos diseños que incorporan pruebas de validez podrían agilizar las retiros, acelerando potencialmente el proceso.
3. **Dependencia de la lógica de propiedad de activos 🔑**: La eficacia de Plasma depende de que los activos tengan un propietario claro. Las nuevas propuestas de Plasma tratan de abordar los activos sin una propiedad económica clara, aunque las garantías plenas de seguridad siguen siendo intrincadas.
4. **Complejidad específica de la aplicación 🧩**: Las iteraciones modernas de Plasma intentan reducir los altos niveles de razonamiento específico de la aplicación mejorando la compatibilidad EVM, facilitando así la creación de sistemas similares a Ethereum.
5. **Escalabilidad limitada en aplicaciones complejas 📈**: Los modelos Plasma anteriores eran menos adecuados para aplicaciones complejas. La introducción de capacidades EVM y los avances de ZK-EVM pueden ampliar la escalabilidad de Plasma a aplicaciones más sofisticadas.
6. **Dependencia del Operador para la Gestión de Datos 👥**: Mientras que los modelos iniciales de Plasma dependían de los operadores para la gestión de datos, lo que podía provocar una centralización, los nuevos modelos con pruebas de validez mejoradas pretenden un enfoque más descentralizado, aunque persiste cierta implicación de los operadores.
7. **Cuestiones de disponibilidad de datos 🔒**: La disponibilidad de datos ha sido un problema crítico para Plasma, pero las propuestas emergentes que utilizan ZK-SNARKs podrían mejorar la verificación de datos, facilitando la detección y disputa de transacciones no válidas.
8. **Requisito de Vigilancia del Usuario 👀**: Los usuarios deben vigilar la red o delegar la vigilancia para garantizar la seguridad de los fondos, pesto esto añade complejidad. Sin embargo, los recientes avances de Plasma podrían disminuir esta carga mediante mejores mecanismos de salida y detección de fraudes.

## Óptimo para 🎯

**Seguimiento y Gestión de Activos**

Las aplicaciones que requieren el seguimiento y la gestión de activos pueden beneficiarse de los Plasma chians. A cada activo se le puede asignar un identificador único y realizar un seguimiento eficaz, lo que hace que Plasma sea adecuado para mercados digitales, gestión de la cadena de suministro y plataformas de activos tokenizados.

**Microtransacciones o Pequeñas Transacciones Frecuentes (es decir, centradas en Pagos)**

Plasma es ideal para aplicaciones que implican transacciones frecuentes de poco valor. Esto podría incluir plataformas de juegos, sistemas de micro pagos o cualquier aplicación en la que los usuarios intercambien con frecuencia pequeñas cantidades de poco valor.

**Aplicaciones no financieras**

Debido a sus menores requisitos de capital y a su capacidad para gestionar una amplia gama de transacciones, Plasma también es adecuado para aplicaciones de blockchain no financieras que siguen necesitando las ventajas de la descentralización y de seguridad.

### No apto para

Aplicaciones cuyo objetivo es una transacción instantánea o que implican stransiciones de estado complejas

## Ejemplos y recursos 📚

1. [El desarrollo y la perspectiva de Plasma - Medio\*\*](https://medium.com/@Web3comVC/el-desarrollo-y-la-prospectiva-de-plasma-42eed0838a3f): Este artículo analiza el estado actual y el potencial futuro de Plasma, destacando su espacio de diseño y sus soluciones de escalabilidad.
2. [**Ethereum Plasma: Todo lo que necesitas saber - OKX**](https://www.okx.com/learn/ethereum-plasma-guide): Una guía que explora Ethereum Plasma, detallando cómo crea cadenas más pequeñas sobre un _child chain_ existente y sus implicaciones para el ecosistema blockchain.
3. [**Implementación de investigación de OmiseGO del Plasma Mínimo Viable - GitHub**](https://github.com/omgnetwork/plasma-mvp): Este repositorio de GitHub contiene la implementación de investigación de OmiseGO del Plasma Mínimo Viable, que ofrece una visión práctica de cómo se estructura e implementa el MVP.

### Historia

1. [**Documento original sobre el plasma**](http://plasma.io/plasma-deprecated.pdf) **Agosto de 2017:** El archivo pdf del documento original sobre el plasma
2. [**Plasma Viable Mínimo - Investigación Ethereum**](https://ethresear.ch/t/minimal-viable-plasma/426) **Enero de 2018**: Este recurso proporciona una especificación para una implementación mínima viable de Plasma, discutiendo sus propiedades básicas de seguridad y sus funcionalidades.
3. [**Plasma MVP - Aprende Plasma**](https://www.learnplasma.org/en/learn/mvp.html)**:** Esta página ofrece una visión general de Plasma Más Viable (MoreVP), una extensión de Plasma Mínimo Viable, y explica cómo funciona Plasma MVP.
4. [**Plasma Cash**](https://ethresear.ch/t/plasma-cash-plasma-with-much-less-per-user-data-checking/1298) **Marzo 2018**: Una variante específica del marco Plasma, diseñada para mejorar la escalabilidad y la seguridad.
5. [**Plasma Cashflow**](https://hackmd.io/DgzmJIRjSzCYvl4lUjZXNQ?view#%F0%9F%9A%AA-Exit) **Verano de 2018**: Describe Plasma Cashflow como una adaptación de Plasma Cash, que implica el depósito, la transacción y la salida de una cadena de blockchain específica. También menciona formas de abordar los costos asociados a la validación de tokens, como el uso de zkSNARKs o el checkpointing al estilo de Plasma XT.
6. [**Plasma Prime**](https://ethresear.ch/t/plasma-prime-design-proposal/4222) **Noviembre de 2018:** Esta propuesta profundiza en la utilización del modelo UTXO para definir la propiedad de los activos, la mecánica de las pruebas RSA para la inclusión y exclusión de transacciones dentro de segmentos específicos, la estructura detallada de los Plasma blocks.
7. [**Juegos de salida para Validiums EVM: El retorno de Plasma**](https://vitalik.eth.limo/general/2023/11/14/neoplasma.html) **Noviembre 2023:** El artículo revisa Plasma a la luz de los avances en las pruebas de validez, como las ZK-SNARK, que podrían abordar los principales retos de Plasma, especialmente en la gestión del almacenamiento de datos del lado del cliente. Explora posibles extensiones de Plasma a la EVM con gráficos UTXO paralelos y salida total del estado.
