# 🔐 Validiums

{% hint style="info" %}
Los validiums no pueden considerarse Layer 2 per se. Cuando hablamos de Validiums lo hacemos desde el punto de vista de la Disponibilidad de los Datos.
{% endhint %}

Es un enfoque que las distintas Layers 2 pueden adoptar respecto a sus preocupaciones sobre la Disponibilidad de Datos. Para leer más sobre esto, ve a nuestro desglose que cuenta con mas información sobre Conocimientos generales de Layer 2 data-availability

Como se discute en la página _offchain-data-availability_ ningún proyecto respetable utiliza Validiums puros. Aunque puede utilizarse para casos de uso sin necesidad de seguridad crítica, hay algunos Rollups que utilizan comités de disponibilidad de datos de uso general como parte de su elección de Validium.

{% hint style="info" %}
El siguiente escenario utiliza un DAC Validium sin permiso, comprueba otras variaciones&#x20;
{% endhint %}

## Escenario 🌟

**Peter es un desarrollador que trabaja en un juego multijugador en línea que implica transacciones frecuentes dentro del juego, como intercambiar objetos o monedas en el juego. Está explorando soluciones de Blockchain para mejorar la seguridad y la transparencia, pero le preocupan los elevados costes de transacción y la escalabilidad. Aquí es donde Validium entra en juego.**

### **Entender el Validium**

Validium es una solución de escalado de Layer 2 que ofrece un alto rendimiento y bajos costos de transacción, lo que la convierte en una opción atractiva para las aplicaciones en los juegos. Así es como funciona:

#### **Las Tres Partes en Validium**

1. **Layer 2**: Aquí es donde se registran inicialmente las transacciones de tu juego (como intercambios de objetos o monedas). Es rápida y eficaz, ya que se encarga de la mayor parte del procesamiento de las transacciones.
2. **El Proveedor de Disponibilidad de Datos (DA) fuera de la cadena**: Esta entidad almacena los datos reales de las transacciones fuera de la cadena. En nuestro contexto de juego, esto podría incluir detalles de cada intercambio de objetos, interacciones de los jugadores y otras actividades dentro del juego.
3. **Mainnet de Ethereum**: Es la última capa de seguridad y confianza, donde se producen las validaciones y comprobaciones finales.

**El proceso**

1. **Registro de transacciones en L2**: Cuando un jugador intercambia un objeto en tu juego, esta transacción se registra primero en la Cadena L2.
2. **Manejo de datos por el proveedor de DA de Offchain**: Los datos de esta transacción se envían al proveedor de DA de Offchain. El proveedor se asegura de que los datos estén disponibles y almacenados de forma segura, lo que es crucial para su posterior verificación.
3. **Firma y envío de la raíz Merkle**: Los validadores del proveedor de DA _offchain_ firman la raíz Merkle de la declaracion de disponibilidad de datos (DA). Esta raíz firmada se envía al Contrato Puente de DA en la red principal de Ethereum.
4. **Publicación de pruebas en la red principal de Ethereum**: Al mismo tiempo, las pruebas de las transacciones de la chain L2 (como el comercio de objetos en tu juego) se publican en la Mainnet de Ethereum. Esto se hace a través del contrato L2 en el Mainnet.
5. **Comprobaciones de fraude y validez**: El contrato L2 en la Mainnet de Ethereum se encarga de las pruebas de fraude y validez. Garantiza que los datos subyacentes de cada transacción (almacenados fuera de la cadena) están disponibles y son válidos a través del contrato DA Bridge.

## ventajas y desventajas :arrow\_up::arrow\_down:

**Ventajas:**

* Estos DAC sin permisos vienen con garantías extraeconómicas sobre la disponibilidad de los datos, porque la comisión puede ser eliminada si tienen un mal comportamiento.
* Son más creíblemente neutrales como Layer DA que como DAC porque existe como cadena independiente por derecho propio como Layer DA de propósito general, en lugar de como Layer DA para una L2 específica de Ethereum.

**Desventajas:**

* Son rentables y menos costosos que los Rollups puros, pero cuanto más descentralizados estén y más firmas necesiten por atestación, más costosos serán.
* Si el proveedor de DA Offchain falla o actúa maliciosamente, existe el riesgo de pérdida de datos. Sin embargo, este riesgo está mitigado por el diseño del sistema y el uso de proveedores de DA de confianza.

#### Ejemplos de estos proveedores de DA

Celestia, Polygon Avail y EigenDA

## Óptimo para 🎯

* Aplicaciones exigentes donde la seguridad no es un problema
* Aplicaciones no financieras
* Juegos
* Ecosistemas gobernados centralmente

##
