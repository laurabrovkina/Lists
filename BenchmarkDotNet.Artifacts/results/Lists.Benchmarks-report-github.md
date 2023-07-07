``` ini

BenchmarkDotNet=v0.13.5, OS=Windows 10 (10.0.19045.3086/22H2/2022Update)
Intel Core i5-3570K CPU 3.40GHz (Ivy Bridge), 1 CPU, 4 logical and 4 physical cores
.NET SDK=7.0.305
  [Host]     : .NET 7.0.8 (7.0.823.31807), X64 RyuJIT AVX
  DefaultJob : .NET 7.0.8 (7.0.823.31807), X64 RyuJIT AVX


```
|           Method |    Size |            Mean |         Error |        StdDev | Allocated |
|----------------- |-------- |----------------:|--------------:|--------------:|----------:|
|              **For** |     **100** |        **90.46 ns** |      **0.464 ns** |      **0.434 ns** |         **-** |
|          Foreach |     100 |        89.55 ns |      0.543 ns |      0.481 ns |         - |
|     Foreach_Linq |     100 |       251.88 ns |      1.273 ns |      1.191 ns |         - |
| Parallel_ForEach |     100 |     2,423.03 ns |     27.143 ns |     25.390 ns |    1996 B |
|    Parallel_Linq |     100 |     2,857.63 ns |     15.985 ns |     14.171 ns |    2840 B |
|     Foreach_Span |     100 |        43.09 ns |      0.187 ns |      0.175 ns |         - |
|         For_Span |     100 |        42.82 ns |      0.295 ns |      0.261 ns |         - |
|              **For** |  **100000** |    **81,451.20 ns** |    **452.835 ns** |    **423.582 ns** |         **-** |
|          Foreach |  100000 |    82,143.77 ns |    821.660 ns |    768.581 ns |         - |
|     Foreach_Linq |  100000 |   244,706.91 ns |  1,096.251 ns |    971.798 ns |         - |
| Parallel_ForEach |  100000 |   187,320.18 ns |  2,481.303 ns |  2,321.012 ns |    2236 B |
|    Parallel_Linq |  100000 |   224,739.42 ns |  4,452.766 ns | 11,885.333 ns |    2849 B |
|     Foreach_Span |  100000 |    27,233.88 ns |    135.169 ns |    119.824 ns |         - |
|         For_Span |  100000 |    27,202.21 ns |    132.840 ns |    124.259 ns |         - |
|              **For** | **1000000** |   **813,863.02 ns** |  **3,892.805 ns** |  **3,450.870 ns** |       **1 B** |
|          Foreach | 1000000 |   815,823.54 ns |  4,694.228 ns |  4,390.983 ns |       1 B |
|     Foreach_Linq | 1000000 | 2,457,919.27 ns | 10,963.796 ns | 10,255.542 ns |       2 B |
| Parallel_ForEach | 1000000 | 1,763,967.37 ns |  3,897.043 ns |  3,454.627 ns |    2249 B |
|    Parallel_Linq | 1000000 | 2,103,964.54 ns | 35,302.402 ns | 29,479.105 ns |    2884 B |
|     Foreach_Span | 1000000 |   274,003.92 ns |  2,251.965 ns |  2,106.489 ns |         - |
|         For_Span | 1000000 |   272,100.76 ns |  1,287.849 ns |  1,204.655 ns |         - |
