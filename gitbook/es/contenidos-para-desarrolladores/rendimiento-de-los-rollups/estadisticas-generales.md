# ⏳ Estadísticas generales

A continuación hemos recopilado información de [rollup.codes](https://www.rollup.codes/) sobre algunos datos generales de los distintos Rollups, con el fin de ofrecer una visión global y una comparación entre estos enfoques.

1. **Tiempo de Bloqueo**:
   * El intervalo de tiempo entre la creación de bloques consecutivos en una Blockchain. En la Layer 2, el tiempo de bloque puede ser significativamente más corto que en la Layer 1 de Ethereum, lo que permite un procesamiento más rápido de las transacciones.
2. **Límite de gas / bloque**:
   * La cantidad máxima de esfuerzo computacional (gas) que se puede gastar en un solo bloque en la Capa 2. Este límite ayuda a gestionar el tamaño del bloque y la velocidad de procesamiento del mismo.
3.  **Objetivo de gas / Bloque**:

    * Similar al límite de gas, se trata de un tope u objetivo más suave para la cantidad de uso de gas por bloque. Las Layer 2 podrían utilizarlo para guiar a los productores de bloques hacia un tamaño de bloque ideal basado en la EIP-1559.

    Lee más aquí: [Qué significa la EIP 4844 para la Layer 2s](../costos-de-transaccion/que-significa-la-eip-4844-para-layer-2s.md)
4. **Frecuencia de secuenciación**:
   * La frecuencia con la que el Rollup publica transacciones L2 en Ethereum L1. El tiempo varía en función de la cantidad de calldata que debe publicarse en L1
5. **Finalidad**:
   * El tiempo que tardan las transacciones en considerarse irreversibles. En la Layer 2, la finalidad suele depender de la Blockchain de Layer 1 subyacente (Ethereum), ya que la Layer 2 envía periódicamente actualizaciones de estado a la Layer 1.

<table data-full-width="true"><thead><tr><th width="190">Métricas</th><th width="125">Ethereum</th><th width="134">OP Mainnet (Optimistic, EVM)</th><th width="128">Base (optimistic, EVM)</th><th width="226">Linea (zk, EVM)</th><th width="151">Arbitrum One (Optimistic, EVM)</th><th width="146">Polygon zkEVM</th><th>zkSync Era (ZK, EVM)</th></tr></thead><tbody><tr><td>Tiempo de Bloqueo</td><td>12 segundos</td><td>2 segundos</td><td>2 segundos</td><td>12 segundos</td><td>250ms</td><td>Irregular*</td><td>5 segundos</td></tr><tr><td>Límite de Gas / Bloqueo</td><td>30 millones</td><td>30 millones</td><td>30 millones</td><td>61 millones</td><td>32 millones</td><td>30 millones</td><td>80 millones</td></tr><tr><td>Objetivo de gas / Bloque*</td><td>15 millones</td><td>5 millones</td><td>5 millones</td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Cargo base de la Layer 2</td><td>-</td><td>a añadir</td><td>a añadir</td><td>a añadir</td><td>a añadir</td><td>a añadir</td><td>a añadir</td></tr><tr><td>Frecuencia de secuenciación</td><td>-</td><td>0. 5 - 2 minutos</td><td>0,5 - 2 minutos</td><td>0,5 - 2 minutos</td><td>0. 5 - 2 minutos</td><td>~4-8 minutos</td><td>~6-15 minutos</td></tr><tr><td>Finalidad</td><td>12-13 minutos</td><td>7 días</td><td>7 días</td><td>8 - 32 horas</td><td>7 días</td><td>~1 hora</td><td>24 horas</td></tr></tbody></table>

###
