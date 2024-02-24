# 🌀 Rollups

### **Comprender el panorama de la Layer 2:**

1. **Plasma y State Channels- Esquemas completos de Layer 2**: Plasma y los State Channels intentan trasladar tanto los datos como el cálculo _off-chain_. Sin embargo, se enfrentan a retos fundamentales de la teoría de juegos relacionados con la disponibilidad de los datos, lo que dificulta el soporte seguro de todas las aplicaciones. Se basan en una noción explícita de propiedad de activos, limitando su generalidad.
2. **Rollups - Un enfoque híbrido**: Los Rollups representan un esquema híbrido de Layer 2. Trasladan el cálculo y el almacenamiento de estado _off-chain_, pero conservan algunos datos de cada transacción en la Layer 1 (Ethereum). Este enfoque equilibra la eficiencia _off-chain_ con la integridad de los datos _on-chain_.

## Escenario 🌟

**Consideremos una plataforma de crowdfunding que utiliza Rollups para gestionar y asegurar eficazmente sus transacciones. Esta plataforma permite a los emprendedores presentar sus proyectos y recibir financiación de los participantes y donadores. He aquí cómo se utilizan los Rollups en este escenario:**

### **Configurar el Rollup:**

1. **Smart contract con State Root**📜🌳: La plataforma funciona con un smart contract en la blockchain de Ethereum. Este contrato mantiene un State Root, que es la raíz de Merkle del estado del rollup, que engloba los saldos de las cuentas, los detalles de los proyectos, las cantidades de financiación y otros datos relevantes dentro del rollup.
2. **Publicación de lotes**🗜️: Los emprendedores publican sus proyectos y los participantes los financian. Estas actividades generan numerosas transacciones. Periódicamente, se recopila un lote de estas transacciones de forma muy comprimida. Cada lote incluye el State Root anterior y una nueva State Root, que refleja el estado después de procesar estas transacciones.
3. **Verificación del contrato**✅: Cuando se envía un lote a la blockchain, el smart contract verifica que el State Root del lote coincide con su State Root actual. Si se confirma la coincidencia, el contrato actualiza el State Root.

### **Pagos y retiradas:**

1. **Depósito de fondos**: Cuando los participantes quieren financiar un proyecto, pueden depositar sus fondos en el rollup. Estas transacciones tienen entradas desde fuera del estado de rollup. La transacción que envía el lote debe transferir estos activos al contrato de rollup.
2. **Retirada de fondos**: Si un proyecto alcanza su objetivo de financiación y el emprendedor retira los fondos, o si un participante retira su inversion, estas transacciones tienen salidas al exterior. Al procesar el lote, el smart contract inicia estas retiradas.

### \*\*Asegurar la integridad de las actualizaciones estatales:##\#

El reto clave es garantizar que las raíces post-estado de los lotes sean correctas. Si alguien pudiera enviar un lote con cualquier raíz post-estado sin consecuencias, podría, por ejemplo, redirigir fondos ilegítimamente. Para evitarlo, el rollup utiliza una de las dos soluciones principales:

1. Enrollamientos optimistas
2. Rollups de Conocimiento Cero

## ventajas y desventajas :arrow\_up::arrow\_down:

### Ventajas

1. **Escalabilidad y eficiencia mejoradas** 🗜️: Los Rollups emplean métodos de compresión avanzados para minimizar la huella de datos en la cadena. Al sustituir datos por computación siempre que es posible, mejora significativamente la eficiencia.
2. **Transacciones rentables** 📈: Al utilizar técnicas avanzadas de compresión, los Rollups reducen la huella de datos en la cadena, lo que se traduce en menores costes de gas. Por ejemplo, una transferencia de tokens ERC20 en un rollup puede costar menos de 300 en costes de gas, frente a unos 45.000 de gas en la Layer base de Ethereum.
3. **Seguridad mejorada** :cerrado\_bloqueo\_con\_clave:: Los Rollups mantienen una parte de los datos onchain, garantizando la integridad y seguridad de las transacciones. Esto es crucial para las aplicaciones en las que la confianza y la transparencia son primordiales.

### Inconvenientes

1. **Requisitos de hardware y costes para ZK-Rollups**:
   * 💻 **Intensidad de hardware**: La generación de pruebas de zero-knowledge, un componente clave de los ZK-Rollups, requiere una potencia de cálculo significativa, que puede ser intensiva en hardware.
   * 💸 **Implicaciones de coste**: Este requisito de hardware puede traducirse en costes más elevados, haciendo potencialmente que los ZK-Rollups sean una opción menos accesible para algunos usuarios o desarrolladores, especialmente los que tienen recursos limitados.
2. **Retrasos de retirada en los Rollups Optimistas**:
   * ⏳ **Retrasos del Periodo de Desafío**: Los Rollups Optimistas incluyen un periodo de impugnación para garantizar la integridad de la transacción. Este periodo puede provocar retrasos en la retirada de fondos.
   * 🕒 **No es ideal para transacciones sensibles al tiempo**: Estos retrasos pueden ser un inconveniente para las transacciones en las que el tiempo es esencial, ya que no se garantiza el acceso inmediato a los fondos.
3. **Limitaciones del ancho de banda de datos**:
   * 🌐 **Limitaciones subyacentes de la Blockchain**: Aunque los Rollups mejoran significativamente la escalabilidad, siguen estando sujetos a las limitaciones de ancho de banda de datos de la cadena de bloques subyacente (por ejemplo, Ethereum).
   * 🚧 **Techo de escalabilidad**: Esto significa que, a pesar de su eficiencia, los Rollups no pueden alcanzar una escalabilidad infinita y están sujetos a las limitaciones de rendimiento de la Layer base.
4. **Complejidad en la Implementación**:
   * 🧠 **Complejidad Técnica**: La implementación de los Rollups, en particular de los ZK-Rollups, implica técnicas criptográficas avanzadas, lo que añade una Layer de complejidad.
   * 🛠️ **Desafíos para el desarrollo**: Esta complejidad puede plantear retos para los desarrolladores, ya que requiere conocimientos y habilidades especializados en criptografía y tecnología blockchain.

## Óptimo Para 🎯

{% hint style="info" %}
Alterna para ver cuáles podrían ser estas aplicaciones
{% endhint %}

<details>

<summary>Propósito general y aplicaciones complejas</summary>

1. **Aplicaciones DeFi**: En el espacio de las finanzas descentralizadas (DeFi), los Rollups pueden ser especialmente útiles. Proporcionan la escalabilidad necesaria para gestionar transacciones e interacciones financieras complejas, como el comercio, los préstamos y los empréstitos, al tiempo que garantizan la seguridad y la integridad de los datos.
2. **Mercados NFT**: Para las plataformas de tokens no fungibles (NFT), los Rollups ofrecen una forma eficaz de gestionar un gran volumen de actividades como por ejemplo: mintear, compra o venta. Reducen los costes de gas asociados a estas transacciones, haciendo más accesible el comercio de NFT.
3. **Ejecución Inteligente de Contratos**: Los Rollups son muy adecuados para aplicaciones que requieren complejas interacciones de contratos inteligentes. Al descargar la computación fuera de la cadena, permiten que los contratos más complejos e intensivos en computación se ejecuten de forma más eficiente que en la cadena principal.
4. **Interacciones a través de la cadena**: Para las aplicaciones que requieren interacciones a través de diferentes redes de blockchain, los Rollups pueden facilitar transacciones y comunicaciones entre cadenas más eficientes.
5. **Aplicaciones centradas en la privacidad**: Especialmente con los ZK-Rollups, hay una capa añadida de privacidad, ya que los datos de las transacciones se comprimen y validan mediante pruebas de zero-knowledge, lo que los hace adecuados para aplicaciones que dan prioridad a la privacidad del usuario.
6. **DApps escalables (aplicaciones descentralizadas)**: Las DApps que pretenden escalar sin comprometer la seguridad y la descentralización se benefician de los Rollups. Pueden gestionar más usuarios y transacciones sin los típicos cuellos de botella de la cadena de bloques principal.
7. **Soluciones empresariales de cadena de bloques**: Para los negocios y empresas que buscan aprovechar la tecnología blockchain para la gestión de la cadena de suministro, la verificación de la identidad y otras aplicaciones, los Rollups ofrecen una solución escalable y eficiente.

</details>

## Fuentes y Material Extra

{% embed url="https://ethereum.org/en/developers/docs/scaling/zk-rollups/" %}

{% embed url="https://ethereum.org/en/developers/docs/scaling/optimistic-rollups/" %}

{% hint style="warning" %}
Si sólo estás interesado en saber cuál de los Rollups Optimista y Cero Conocimientos se adaptaría mejor a tu proyecto, ve directamente a la página  para ver su comparación y perspectivas.
{% endhint %}
