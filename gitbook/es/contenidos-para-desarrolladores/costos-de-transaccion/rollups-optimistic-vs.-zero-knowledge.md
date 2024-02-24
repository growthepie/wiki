# ⚔️ Rollups Optimistic vs. Zero Knowledge

## Una rápida visión general

### **Rollups Optimistic (por ejemplo, Arbitrum, Optimism)**:

* **Mecanismo**: Se basan en un sistema de pruebas de fraude. El contrato de Rollups mantiene un historial completo de las raíces de los estados y el hash de cada lote de transacciones.
* **Pruebas de fraude**: Si alguien detecta un _state-root_ posterior incorrecta en un lote, puede enviar una prueba de fraude a la blockchain. Esta prueba demuestra que el lote se calculó incorrectamente.
* **Verificación y reversión**: El contrato verifica la prueba de fraude. Si descubre que el lote es realmente incorrecto, revierte ese lote y todos los siguientes, manteniendo la integridad del sistema.
* **Supuesto de honradez**: Los Rollups Optimistic funcionan bajo el supuesto de que todas las transacciones son válidas por defecto, y sólo en caso de fraude se exigen y comprueban las pruebas.

#### Cálculo de las comisiones por transacción

* Optimistic = (datos L1 publicación gas \* precio L1 gas) + (uso gas en L2 \* precio l2 gas)

### **ZK-Rollups (por ejemplo, zkSync Era, Polygon zkEVM)**:

* **Mecanismo**: Utilizan pruebas de validez, en concreto ZK-SNARK (Argumento Sucinto de Conocimiento Cero No Interactivo), para garantizar la corrección de las transacciones.
* **Pruebas Criptográficas**: Cada lote incluye un ZK-SNARK, que prueba criptográficamente que el state-root posterior estado es el resultado correcto de ejecutar el lote.
* **Verificación eficiente**: Independientemente del tamaño del cálculo, el ZK-SNARK puede verificarse rápidamente en el chain, garantizando que sólo se aceptan cambios de estado válidos.&#x20;
* **Finalidad inmediata**: A diferencia de los Optimistic Rollups, los ZK Rollups proporcionan una finalidad inmediata, ya que la validez de cada lote se comprueba y verifica antes de ser aceptado en el blockchain.

#### Cálculo de las comisiones por transacción

* Conocimiento\_cero = ((L1 publicación de datos + L1 costos de prueba) \* L1 precio del gas) + (uso del gas en L2 \* l2 precio del gas)

## Comparación y perspectivas

.

> "En general, mi opinión es que, a corto plazo, es probable que los Optimistics Rollups triunfen en el cálculo EVM de uso general y que los Rollups ZK triunfen en los pagos sencillos, el intercambio y otros casos de uso de aplicaciones específicas, pero a mediano y largo plazo los Rollups ZK triunfarán en todos los casos de uso a medida que mejore la tecnología ZK-SNARK".
>
> Vitalik Buterin

## Escenario 🌟

Imagina que eres un desarrollador que trabaja en dos proyectos diferentes de blockchain: un mercado descentralizado (Proyecto A) y una plataforma de trading de alta frecuencia (Proyecto B). Estás considerando utilizar soluciones de Layer 2 para optimizar la eficiencia y el costo de las transacciones, y estás indeciso entre los Optimistic Rollups y los ZK Rollups. Comprender las diferencias en sus costos y funcionalidades es crucial para tu decisión.

### **Proyecto A: Mercado Descentralizado - Optimistic Rollups**&#x20;

* **Naturaleza del proyecto**: Este mercado implica varias transacciones, como anunciar artículos, pujar y ventas finales. La finalidad inmediata de las transacciones no es crítica, ya que suele haber un periodo de espera para que concluyan las pujas y las ventas.
* **¿Por qué Optimistic Rollups ?**:
  * Simplicidad\*\*: Los Optimistic Rollups  son sencillos y se ajustan a la estructura de transacciones menos compleja del mercado.
  * Preparación para la adopción: Están más cerca de la adopción generalizada, por lo que ofrecen un entorno más estable y probado.
  * **Consideración de costos**: Aunque conllevan mayores costos de gas en el chain, la frecuencia de las transacciones en un mercado (no demasiado alta) hace que sea un gasto asumible.
  * **Periodo de retirada**: El periodo de retirada más largo no es una preocupación importante, ya que las transacciones del mercado no exigen una finalidad inmediata.

### **Proyecto B: Plataforma de trading de alta frecuencia - ZK Rollups**

* **Naturaleza del proyecto**: Esta plataforma requiere un procesamiento rápido de las transacciones debido al gran volumen y al rápido ritmo de las operaciones.
* ¿Por qué ZK Rollups?
  * Finalidad inmediata\*\*: Los ZK Rollups ofrecen una finalidad instantánea de las transacciones, crucial para la naturaleza dinámica del comercio.
  * **Menores costos de gas**: Proporcionan menores costos de gas por transacción, una ventaja significativa dado el alto volumen de operaciones.
  * **Compensación de complejidad**: La complejidad y los mayores costos de cálculo fuera de la cadena son compensaciones aceptables por las ganancias de eficiencia en un entorno comercial. **Desafío de la generalización**: Aunque es más difícil de generalizar, la naturaleza específica de la negociación de alta frecuencia encaja bien con las capacidades de los ZK Rollups.

## **Diferencias clave**

* **Eficiencia de costos**: Para el Proyecto A (mercado), los mayores costos de gas en cadena de los Optimistic Rollups se ven compensados por la menor frecuencia de las transacciones. En cambio, el Proyecto B (plataforma de trading) se beneficia de los menores costos por transacción de los Rollups ZK debido a su elevado volumen de transacciones.
* **Finalidad de la transacción**: El mercado puede permitirse el periodo de validez más largo de los Optimistic Rollups, mientras que la plataforma de negociación se beneficia de la validez inmediata de los Rollups ZK.
* Complejidad técnica\*\*: La tecnología más sencilla de Optimistic Rollups se ajusta a las necesidades del mercado, mientras que la plataforma de negociación puede aprovechar la tecnología avanzada de ZK Rollups a pesar de su complejidad.

## Resumen

### Optimistic Rollups&#x20;

* Más sencillo y más próximo a la adopción generalizada;
* Adecuado para aplicaciones en las que la finalidad inmediata es menos crítica.
* Preferible para escenarios que requieren un enfoque tecnológico más sencillo.
* Conllevan mayores costos de gas en cadena. Presentan un periodo de retirada más largo.

### ZK Rollups

* Ofrecen una finalidad inmediata de la transacción.
* Proporcionan menores costos de gas por transacción, ideales para entornos de gran volumen y ritmo rápido.
* La complejidad y los mayores costos de computación fuera de la cadena son compensaciones notables.
* Más difícil de generalizar para aplicaciones amplias.
* Tecnología en rápida evolución.

## Fuentes y Material Extra

1. [**Una guía incompleta sobre los Rollups - Blog de Vitalik Buterin**](https://vitalik.ca/general/2021/01/05/rollup.html): Esta completa guía de Vitalik Buterin profundiza en el concepto de Rollups como solución clave de escalabilidad para Ethereum. Abarca los antecedentes del escalado de layer 1 y layer 2, la mecánica de los State Channels, el plasma y los rollups, y las distinciones entre rollups optimistas y ZK. El artículo también aborda los retos y el potencial de los Rollups para mejorar la escalabilidad de la Blockchain.
2. [**La paradoja L2**](https://twitter.com/joel\_john95/status/1727628204964225027)**:** Un hilo de lectura obligada muy interesante que analiza el estado actual de los Rollups y plantea preguntas importantes.
3. [**ZK-Rollups vs. Optimistic Rollups: Comprender las diferencias - Nervos Network**](https://www.nervos.org/knowledge-base/zk\_rollup\_vs\_optimistic\_rollup)**:** Contrasta sus mecanismos operativos, centrándose especialmente en sus enfoques de la validación de transacciones y el tratamiento de datos.

{% embed url="https://twitter.com/joel_john95/status/1727628204964225027" %}
