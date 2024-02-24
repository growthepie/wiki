# 📨 Latencia y coste de la mensajería

### **Mensajería**

* El Rollups permite una comunicación sin fisuras con la Layer 1, posibilitando la transmisión de mensajes arbitrarios.
* Cada protocolo garantiza la transferencia verificable de datos a la cadena prevista.

**Latencia de L1 a L2**:

* Se refiere a la duración necesaria para que un mensaje sea accesible en el Rollup una vez incluido en un bloque de Ethereum.

**Coste de L1 a L2**:

* El gasto que supone enviar un mensaje desde Ethereum al Rollup de Layer 2.
* El Rollup procesa el mensaje utilizando una dirección del sistema, actuando en nombre del remitente original de la Layer 1.
* El remitente de la Layer 1 soporta el coste del gas de la Layer 2 para la ejecución del mensaje.

**Latencia de L2 a L1**:

* Es el tiempo que tarda un mensaje en estar disponible en Ethereum después de ser registrado en un bloque Rollup y secuenciado a la Layer 1.

**Coste de L2 a L1**:

* El gasto de gas en que se incurre para la verificación e inicio de la ejecución del mensaje en Ethereum, tras su envío desde el Rollup.
* Este coste lo cubre la Cuenta de Propiedad Externa (EOA) que desencadena la transacción de reclamación en la Layer 1.
* Es importante señalar que este coste no incluye los gastos derivados de las operaciones realizadas como consecuencia del mensaje.

<table data-full-width="true"><thead><tr><th>Mensajes</th><th>OP Mainnet (Optimistic, EVM)</th><th>Base (Optimistic, EVM)</th><th>Linea (zk, EVM)</th><th>Arbitrum One (Optimistic, EVM)</th><th>Polygon zkEVM</th><th>zkSync Era (ZK, EVM)</th></tr></thead><tbody><tr><td>L1 → L2 Latencia</td><td>~1 minuto</td><td>~1 minuto</td><td>~17min</td><td>~6-9 minutos</td><td>~6-8 minutos</td><td>~2 minutos</td></tr><tr><td>L1 → L2 Coste</td><td>~38 000 gas L1</td><td>~43 000 gas L1</td><td>~66 000 gas L1 + ~71 000 gas L2 (en caso de suministro manual)</td><td>Sin coste añadido</td><td>95000 gas L2</td><td>Sin coste añadido</td></tr><tr><td>L2 → L1 Latencia</td><td>7 días</td><td>7 días</td><td>8 a 32 horas</td><td>7 días</td><td>~1 hora</td><td>-</td></tr><tr><td>L2 → L1 Coste</td><td>600 000 gas L1</td><td>600 000 gas L1</td><td>~73 000 gas L2*</td><td>60 000 gas L1</td><td>95000 gas L1</td><td>-</td></tr></tbody></table>

\*En Línea
