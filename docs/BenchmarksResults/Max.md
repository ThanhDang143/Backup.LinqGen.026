﻿## Max

### Source
[Max.cs](../../LinqGen.Benchmarks/Cases/Max.cs)

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
|     **ForLoop** |     **100** |        **75.39 ns** |      **0.227 ns** |      **0.212 ns** |  **0.20** |      **-** |         **-** |        **0.00** |
| ForEachLoop |     100 |        71.98 ns |      0.297 ns |      0.263 ns |  0.19 |      - |         - |        0.00 |
|        Linq |     100 |       383.49 ns |      1.731 ns |      1.446 ns |  1.00 | 0.0153 |      32 B |        1.00 |
|     LinqGen |     100 |        80.82 ns |      0.338 ns |      0.264 ns |  0.21 |      - |         - |        0.00 |
|  StructLinq |     100 |        78.06 ns |      0.544 ns |      0.425 ns |  0.20 |      - |         - |        0.00 |
|             |         |                 |               |               |       |        |           |             |
|     **ForLoop** |   **10000** |     **6,473.31 ns** |     **33.968 ns** |     **30.112 ns** |  **0.20** |      **-** |         **-** |        **0.00** |
| ForEachLoop |   10000 |     6,536.37 ns |     72.035 ns |     67.381 ns |  0.20 |      - |         - |        0.00 |
|        Linq |   10000 |    32,255.75 ns |     88.708 ns |     82.977 ns |  1.00 |      - |      32 B |        1.00 |
|     LinqGen |   10000 |     7,783.42 ns |     28.203 ns |     25.001 ns |  0.24 |      - |         - |        0.00 |
|  StructLinq |   10000 |     6,453.61 ns |     46.835 ns |     43.810 ns |  0.20 |      - |         - |        0.00 |
|             |         |                 |               |               |       |        |           |             |
|     **ForLoop** | **1000000** |   **648,274.06 ns** |  **5,446.653 ns** |  **4,828.316 ns** |  **0.20** |      **-** |       **1 B** |        **0.03** |
| ForEachLoop | 1000000 |   642,037.38 ns |  3,186.705 ns |  2,980.846 ns |  0.20 |      - |       1 B |        0.03 |
|        Linq | 1000000 | 3,225,897.94 ns | 22,249.741 ns | 19,723.816 ns |  1.00 |      - |      35 B |        1.00 |
|     LinqGen | 1000000 |   779,915.92 ns |  1,961.989 ns |  1,531.792 ns |  0.24 |      - |       1 B |        0.03 |
|  StructLinq | 1000000 |   643,283.95 ns |  5,755.204 ns |  5,383.422 ns |  0.20 |      - |       1 B |        0.03 |
