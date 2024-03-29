﻿## ArraySelectToArray

### Source
[ArraySelectToArray.cs](../../LinqGen.Benchmarks/Cases/ArraySelectToArray.cs)

### Results:
``` ini

BenchmarkDotNet=v0.13.2, OS=macOS Monterey 12.3 (21E230) [Darwin 21.4.0]
Apple M1 Pro, 1 CPU, 10 logical and 10 physical cores
.NET SDK=7.0.101
  [Host]     : .NET 6.0.2 (6.0.222.6406), Arm64 RyuJIT AdvSIMD
  DefaultJob : .NET 6.0.2 (6.0.222.6406), Arm64 RyuJIT AdvSIMD


```
|             Method |   Count |            Mean |         Error |        StdDev |          Median | Ratio | RatioSD |     Gen0 |     Gen1 |     Gen2 | Allocated | Alloc Ratio |
|------------------- |-------- |----------------:|--------------:|--------------:|----------------:|------:|--------:|---------:|---------:|---------:|----------:|------------:|
|               **Linq** |     **100** |       **200.39 ns** |      **1.091 ns** |      **0.967 ns** |       **200.16 ns** |  **1.00** |    **0.00** |   **0.2255** |        **-** |        **-** |     **472 B** |        **1.00** |
|    LinqGenDelegate |     100 |       168.17 ns |      0.316 ns |      0.296 ns |       168.06 ns |  0.84 |    0.00 |   0.2027 |        - |        - |     424 B |        0.90 |
|      LinqGenStruct |     100 |       107.88 ns |      0.448 ns |      0.420 ns |       107.89 ns |  0.54 |    0.00 |   0.2027 |        - |        - |     424 B |        0.90 |
| StructLinqDelegate |     100 |       188.19 ns |      0.443 ns |      0.414 ns |       188.37 ns |  0.94 |    0.00 |   0.2332 |        - |        - |     488 B |        1.03 |
|   StructLinqStruct |     100 |       131.32 ns |      1.016 ns |      0.950 ns |       131.47 ns |  0.65 |    0.01 |   0.2027 |        - |        - |     424 B |        0.90 |
|  HyperLinqDelegate |     100 |       163.82 ns |      1.072 ns |      1.003 ns |       163.43 ns |  0.82 |    0.00 |   0.2027 |        - |        - |     424 B |        0.90 |
|    HyperLinqStruct |     100 |        90.31 ns |      0.947 ns |      0.886 ns |        90.17 ns |  0.45 |    0.01 |   0.2027 |        - |        - |     424 B |        0.90 |
|                    |         |                 |               |               |                 |       |         |          |          |          |           |             |
|               **Linq** |   **10000** |    **14,675.11 ns** |    **267.221 ns** |    **249.958 ns** |    **14,549.82 ns** |  **1.00** |    **0.00** |  **18.8599** |        **-** |        **-** |   **40072 B** |        **1.00** |
|    LinqGenDelegate |   10000 |    15,690.63 ns |     93.591 ns |     87.545 ns |    15,685.96 ns |  1.07 |    0.02 |  18.8599 |        - |        - |   40024 B |        1.00 |
|      LinqGenStruct |   10000 |     9,828.66 ns |     66.832 ns |     55.808 ns |     9,822.38 ns |  0.67 |    0.01 |  18.8599 |        - |        - |   40024 B |        1.00 |
| StructLinqDelegate |   10000 |    15,126.77 ns |    116.633 ns |     97.394 ns |    15,147.07 ns |  1.03 |    0.02 |  18.8599 |        - |        - |   40088 B |        1.00 |
|   StructLinqStruct |   10000 |     8,692.83 ns |     41.162 ns |     38.502 ns |     8,671.31 ns |  0.59 |    0.01 |  18.8599 |        - |        - |   40024 B |        1.00 |
|  HyperLinqDelegate |   10000 |    14,630.28 ns |     69.396 ns |     57.949 ns |    14,630.58 ns |  1.00 |    0.02 |  18.8599 |        - |        - |   40024 B |        1.00 |
|    HyperLinqStruct |   10000 |     7,715.35 ns |     94.805 ns |     84.043 ns |     7,695.39 ns |  0.53 |    0.01 |  18.8599 |        - |        - |   40024 B |        1.00 |
|                    |         |                 |               |               |                 |       |         |          |          |          |           |             |
|               **Linq** | **1000000** | **1,667,471.15 ns** | **30,565.244 ns** | **30,019.157 ns** | **1,652,699.87 ns** |  **1.00** |    **0.00** | **126.9531** | **126.9531** | **126.9531** | **4000188 B** |        **1.00** |
|    LinqGenDelegate | 1000000 | 1,743,528.31 ns | 28,724.432 ns | 26,868.851 ns | 1,743,343.59 ns |  1.05 |    0.01 | 109.3750 | 109.3750 | 109.3750 | 4000097 B |        1.00 |
|      LinqGenStruct | 1000000 | 1,091,038.61 ns | 21,503.553 ns | 51,105.470 ns | 1,074,036.29 ns |  0.64 |    0.02 | 175.7813 | 175.7813 | 175.7813 | 4000141 B |        1.00 |
| StructLinqDelegate | 1000000 | 1,712,953.46 ns | 33,364.440 ns | 48,905.164 ns | 1,727,737.06 ns |  1.01 |    0.03 | 105.4688 | 105.4688 | 105.4688 | 4000175 B |        1.00 |
|   StructLinqStruct | 1000000 |   979,296.66 ns | 10,250.561 ns |  8,002.964 ns |   975,692.87 ns |  0.59 |    0.01 | 152.3438 | 152.3438 | 152.3438 | 4000125 B |        1.00 |
|  HyperLinqDelegate | 1000000 | 1,620,772.53 ns | 26,634.664 ns | 20,794.593 ns | 1,617,750.16 ns |  0.98 |    0.01 | 101.5625 | 101.5625 | 101.5625 | 4000092 B |        1.00 |
|    HyperLinqStruct | 1000000 |   917,997.71 ns | 20,472.819 ns | 56,388.089 ns |   905,379.01 ns |  0.55 |    0.03 | 154.2969 | 154.2969 | 154.2969 | 4000126 B |        1.00 |
