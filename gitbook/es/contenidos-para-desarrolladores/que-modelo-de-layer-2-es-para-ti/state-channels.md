# ↔️ State Channels

### **STATE CHANNELS** <a href="#s2ihq4r793uh" id="s2ihq4r793uh"></a>

"Los state channels son una forma muy amplia y sencilla de pensar en interacciones blockchain que _podrían_ ocurrir en el blockchain, pero en cambio se llevan a cabo _fuera_ del blockchain, sin aumentar de manera significativa el riesgo de cualquier participante."

[**Jeff Coleman**](https://www.jeffcoleman.ca/author/jeff/)

### **Escenario 🌟** <a href="#ap1b3eqjdgqp" id="ap1b3eqjdgqp"></a>

**Imagina un escenario donde Emily tiene una cafetería ☕, y Jack es un cliente frecuente. Jack prefiere pagar su café en pequeñas cuotas, a razón de $2 por taza. Para agilizar este proceso y evitar numerosas transacciones pequeñas, deciden usar una solución de Layer 2: State Channel.**

#### **Proceso:** <a href="#wrnp40awgrkh" id="wrnp40awgrkh"></a>

1. **Configuración Inicial**: Jack deposita $20 (o su equivalente en ETH o una stablecoin) en un _smart contract_. Este depósito es como una tarjeta de café prepago ☕💳, destinada a sus futuras compras
2. **Comprar Café**: Cada vez que Jack compra una taza de café, envía un "ticket" digital _off-chain_ a Emily. El primer billete está marcado con "$2", lo que representa el pago por la primera taza. Para su segunda taza, envía un billete marcado "$4" y este patrón continúa con cada compra.
3. **Cerrar la Cuenta**: Cuando Jack decide saldar su cuenta, Emily presenta el último ticket – digamos que cuesta "$16" después de 8 tazas de café – a la blockchain. El contrato inteligente verifica las firmas de ambas partes, transfiere $16 a Emily y reembolsa los $4 restantes a Jack 💰.
4. **Medidas de Seguridad**: Si Emily por cualquier razón no cierra el _channel_, Jack puede iniciar un período de retiro de 7 días 🗓️. Si Emily no envía el ticket de mayor valor dentro de este período, el _smart-contract_ reembolsará automáticamente el depósito completo de Jack. 🛡️🔒

#### **Ventajas y Desventajas** <a href="#u93zd6jjf3hl" id="u93zd6jjf3hl"></a>

**Ventajas:**

1. **Microtransacciones Eficientes** 💰: En escenarios como la cafetería de Emily, los _state channels_ permiten transacciones pequeñas y frecuentes (como comprar café) sin congestionar la blockchain. Esto es similar a que Jack compre su café de $2 sin necesitar una transacción de blockchain por cada taza.
2. **Flexible y Versátil** 🤹: Estos _channels_ pueden manejar varios tipos de transacciones, desde pagos simples hasta contratos complejos. Por ejemplo, si Emily decide ofrecer un programa de fidelización o descuentos especiales dentro del mismo _state channel_, se podría integrar fácilmente.
3. **Redes Interconectadas** 🔗: Si Emily tiene un _channe_l con Jack y Jack tiene otro con otro proveedor, las transacciones pueden facilitarse indirectamente, creando una red de _state channels_ interconectados.
4. **Propiedades de Privacidad Fuertes** 🕵️‍♂️ : Las transacciones dentro de un _state channel_ son privadas y se comparten únicamente entre los participantes.
5. **Finalidad Instantánea** ⚡: Las actualizaciones de estado se consideran definitivas tan pronto como ambas partes firman, lo que ofrece una alta garantía de aplicabilidad en la cadena.

**Desventajas:**

1. **Limitado a Participantes de la Cadena** 🔒: Los _state channels_ no se pueden utilizar para enviar fondos _off-chain_ a personas que aún no son participantes.
2. **Bloqueo de Capital** 💸: El depósito inicial de Jack queda bloqueado en el _channel_ hasta que se liquiden las transacciones. Esto puede ser una desventaja para los usuarios que no quieren que sus fondos estén inmovilizados, de manera similar a cómo los _state channels_ más grandes y complejos requieren un capital bloqueado significativo.
3. **Complejidad Operativa** 🛠️: Gestionar un _state channel_, especialmente para acuerdos más complejos, puede ser un desafío técnico. En el escenario de la cafetería, si Emily quiere integrar servicios más sofisticados en el _channel_, requeriría una comprensión y una gestión más profundas de la tecnología blockchain.
4. **Requisito de Disponibilidad del 100%** 🚨: Todos los participantes deben estar constantemente disponibles, ya que la falta de disponibilidad podría resultar costosa. Si bien se pueden utilizar representantes, pueden existir riesgos de ataque o soborno.

🎯 Óptimo para:

### Conjuntos de participantes definidos <a href="#id-6thmmymgb4t3" id="id-6thmmymgb4t3"></a>

Los state channels requieren direcciones de participantes conocidos y, a diferencia de las cadenas laterales, el cambio de participantes requiere modificaciones del contrato

### Intercambios frecuentes y a largo plazo <a href="#bahallti03lg" id="bahallti03lg"></a>

Debido al costo inicial de configurar un state channel, son más eficientes para un uso a largo plazo con muchas actualizaciones de estado.

Ejemplos y recursos 📚

1. [**State Channel Applications by Liam Horne - Medium**](https://medium.com/statechannels/state-channel-applications-1f170e7d542e): Este artículo puede proporcionar información sobre por qué es difícil diseñar state channels en Ethereum ahora, cómo se podrían aplicar los state channels en varios modelos de negocios y una descripción técnica de las capas necesarias en un state channel.
2. [**Building a State Channel Application - Devcon Archive**](https://archive.devcon.org/archive/watch/4/building-a-state-channel-application/?playlist=Devcon%204): Charla de Tom Close en Magmo, donde habla sobre las dificultades de construir state channels. y la gestión en el contexto del juego de "piedra, papel o tijera" que construyeron con los state channels.
3. [**Difference Between SideChains and State Channels - Thomas J. Ackermann**](https://www.bgp4.com/2019/05/15/difference-between-sidechains-and-state-channels/): Útil para comprender los aspectos técnicos de los state channels, lo que podría resultar útil para implementaciones complejas en un entorno empresarial.
4. [**State Channel as a Service Based on a Distributed and Decentralized Web - IEEE Xplore**](https://ieeexplore.ieee.org/iel7/6287639/8948470/09050808.pdf): Este recurso explora aplicaciones avanzadas de los state channels, que podrían inspirar usos innovadores en varios modelos de negocios, incluidas las industrias minoristas o de servicios como una cafetería.
5. [**An Incomplete Guide to Rollups**](https://vitalik.ca/general/2021/01/05/rollup.html)**:** Artículo de Vitalik Buterin del 5 de enero de 2021 sobre Rollups.
6. [**State Channels**](https://www.jeffcoleman.ca/state-channels/)**:** El artículo de Jeff Coleman proporciona una explicación completa de los state channels y sus componentes.
