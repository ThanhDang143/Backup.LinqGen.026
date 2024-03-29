﻿## MaxBy

### Source
[MaxBy.cs](../../LinqGen.Benchmarks/Cases/MaxBy.cs)

### Results:
``` ini

BenchmarkDotNet=v0.13.2, OS=macOS Monterey 12.3 (21E230) [Darwin 21.4.0]
Apple M1 Pro, 1 CPU, 10 logical and 10 physical cores
.NET SDK=7.0.101
  [Host]     : .NET 6.0.2 (6.0.222.6406), Arm64 RyuJIT AdvSIMD
  DefaultJob : .NET 6.0.2 (6.0.222.6406), Arm64 RyuJIT AdvSIMD


```
|      Method |   Count |            Mean |         Error |        StdDev | Ratio |   Gen0 | Allocated | Alloc Ratio |
|------------ |-------- |----------------:|--------------:|--------------:|------:|-------:|----------:|------------:|
|     **ForLoop** |     **100** |        **79.56 ns** |      **0.318 ns** |      **0.282 ns** |  **0.16** |      **-** |         **-** |        **0.00** |
| ForEachLoop |     100 |        70.64 ns |      0.236 ns |      0.210 ns |  0.15 |      - |         - |        0.00 |
|        Linq |     100 |       485.11 ns |      2.051 ns |      1.918 ns |  1.00 | 0.0153 |      32 B |        1.00 |
|     LinqGen |     100 |        81.46 ns |      0.408 ns |      0.382 ns |  0.17 |      - |         - |        0.00 |
|             |         |                 |               |               |       |        |           |             |
|     **ForLoop** |   **10000** |     **7,233.35 ns** |     **24.058 ns** |     **22.504 ns** |  **0.17** |      **-** |         **-** |        **0.00** |
| ForEachLoop |   10000 |     6,403.25 ns |     23.151 ns |     21.655 ns |  0.15 |      - |         - |        0.00 |
|        Linq |   10000 |    42,984.01 ns |    183.959 ns |    163.075 ns |  1.00 |      - |      32 B |        1.00 |
|     LinqGen |   10000 |     8,785.19 ns |     34.219 ns |     32.008 ns |  0.20 |      - |         - |        0.00 |
|             |         |                 |               |               |       |        |           |             |
|     **ForLoop** | **1000000** |   **719,690.86 ns** |  **2,305.913 ns** |  **2,156.953 ns** |  **0.17** |      **-** |       **1 B** |        **0.03** |
| ForEachLoop | 1000000 |   644,151.14 ns |  3,412.278 ns |  2,849.406 ns |  0.15 |      - |       1 B |        0.03 |
|        Linq | 1000000 | 4,314,869.58 ns | 38,667.651 ns | 36,169.745 ns |  1.00 |      - |      37 B |        1.00 |
|     LinqGen | 1000000 |   872,163.20 ns |  2,565.569 ns |  2,274.310 ns |  0.20 |      - |       1 B |        0.03 |
