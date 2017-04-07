This is a JMH benchmark comparing techniques for iterating over map entries.

To build:

    mvn clean package

To run:

    java -jar target/benchmarks.jar

To run and profile the garbage collector:

    java -jar target/benchmarks.jar -prof gc

# Summary of the results

Details:
```
# JMH 1.18 (released 25 days ago)
# VM version: JDK 1.8.0_121, VM 25.121-b13
# VM invoker: /usr/lib/jvm/java-8-oracle/jre/bin/java
# VM options: <none>
```

Note this is on Oracle JDK, not OpenJDK.

```
# Run complete. Total time: 00:30:48

Benchmark                                                        (mapImplementation)  (mapIterationStyle)  Mode  Cnt      Score      Error   Units
MapIterationBenchmark.run                                                   HASH_MAP             INTERNAL  avgt   10  10469.725 ±  207.400   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    HASH_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               HASH_MAP             INTERNAL  avgt   10      0.017 ±    0.062    B/op
MapIterationBenchmark.run:·gc.count                                         HASH_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   HASH_MAP   ENTRY_SET_INTERNAL  avgt   10   9771.483 ±  241.082   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.016 ±    0.055    B/op
MapIterationBenchmark.run:·gc.count                                         HASH_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10  10744.608 ±  207.383   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.018 ±    0.062    B/op
MapIterationBenchmark.run:·gc.count                                         HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   HASH_MAP     KEY_SET_INTERNAL  avgt   10  17806.184 ±  789.718   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.028 ±    0.099    B/op
MapIterationBenchmark.run:·gc.count                                         HASH_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   HASH_MAP     KEY_SET_EXTERNAL  avgt   10  19731.242 ±  301.677   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.032 ±    0.114    B/op
MapIterationBenchmark.run:·gc.count                                         HASH_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                            LINKED_HASH_MAP             INTERNAL  avgt   10   5210.174 ±   77.121   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                             LINKED_HASH_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                        LINKED_HASH_MAP             INTERNAL  avgt   10      0.009 ±    0.031    B/op
MapIterationBenchmark.run:·gc.count                                  LINKED_HASH_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                            LINKED_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10   4915.573 ±  105.427   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                             LINKED_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                        LINKED_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.008 ±    0.029    B/op
MapIterationBenchmark.run:·gc.count                                  LINKED_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                            LINKED_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10   6596.840 ±  129.227   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                             LINKED_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                        LINKED_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.011 ±    0.039    B/op
MapIterationBenchmark.run:·gc.count                                  LINKED_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                            LINKED_HASH_MAP     KEY_SET_INTERNAL  avgt   10  12541.554 ±  281.135   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                             LINKED_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                        LINKED_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.020 ±    0.072    B/op
MapIterationBenchmark.run:·gc.count                                  LINKED_HASH_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                            LINKED_HASH_MAP     KEY_SET_EXTERNAL  avgt   10  15863.420 ±  353.675   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                             LINKED_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                        LINKED_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.026 ±    0.090    B/op
MapIterationBenchmark.run:·gc.count                                  LINKED_HASH_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   TREE_MAP             INTERNAL  avgt   10   7878.394 ±   84.650   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    TREE_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               TREE_MAP             INTERNAL  avgt   10      0.013 ±    0.045    B/op
MapIterationBenchmark.run:·gc.count                                         TREE_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   TREE_MAP   ENTRY_SET_INTERNAL  avgt   10   9088.456 ±  247.523   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    TREE_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               TREE_MAP   ENTRY_SET_INTERNAL  avgt   10      0.015 ±    0.051    B/op
MapIterationBenchmark.run:·gc.count                                         TREE_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   TREE_MAP   ENTRY_SET_EXTERNAL  avgt   10   8902.488 ±  229.441   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    TREE_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               TREE_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.015 ±    0.051    B/op
MapIterationBenchmark.run:·gc.count                                         TREE_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   TREE_MAP     KEY_SET_INTERNAL  avgt   10  29167.475 ±  461.090   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    TREE_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               TREE_MAP     KEY_SET_INTERNAL  avgt   10      0.048 ±    0.169    B/op
MapIterationBenchmark.run:·gc.count                                         TREE_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   TREE_MAP     KEY_SET_EXTERNAL  avgt   10  28882.037 ±  649.715   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    TREE_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               TREE_MAP     KEY_SET_EXTERNAL  avgt   10      0.047 ±    0.166    B/op
MapIterationBenchmark.run:·gc.count                                         TREE_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   ENUM_MAP             INTERNAL  avgt   10  14824.432 ±  326.566   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    ENUM_MAP             INTERNAL  avgt   10    264.304 ±    6.535  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               ENUM_MAP             INTERNAL  avgt   10   6176.024 ±    0.086    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                           ENUM_MAP             INTERNAL  avgt   10    267.132 ±   81.446  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                      ENUM_MAP             INTERNAL  avgt   10   6251.188 ± 1960.234    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                       ENUM_MAP             INTERNAL  avgt   10      0.010 ±    0.022  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm                  ENUM_MAP             INTERNAL  avgt   10      0.241 ±    0.512    B/op
MapIterationBenchmark.run:·gc.count                                         ENUM_MAP             INTERNAL  avgt   10     31.000             counts
MapIterationBenchmark.run:·gc.time                                          ENUM_MAP             INTERNAL  avgt   10    115.000                 ms
MapIterationBenchmark.run                                                   ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10  16237.732 ±  603.488   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    241.255 ±    9.189  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10   6176.027 ±    0.094    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                           ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    240.267 ±  104.788  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                      ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10   6152.211 ± 2690.076    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                       ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10      0.010 ±    0.022  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm                  ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10      0.262 ±    0.555    B/op
MapIterationBenchmark.run:·gc.count                                         ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10     21.000             counts
MapIterationBenchmark.run:·gc.time                                          ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    103.000                 ms
MapIterationBenchmark.run                                                   ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10  15973.111 ±  404.864   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10    245.716 ±    6.182  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10   6176.026 ±    0.091    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                           ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10    255.583 ±   48.553  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                      ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10   6423.383 ± 1200.832    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                       ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.008 ±    0.016  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm                  ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.207 ±    0.404    B/op
MapIterationBenchmark.run:·gc.count                                         ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10     28.000             counts
MapIterationBenchmark.run:·gc.time                                          ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10    104.000                 ms
MapIterationBenchmark.run                                                   ENUM_MAP     KEY_SET_INTERNAL  avgt   10  10077.510 ±  207.308   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    ENUM_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               ENUM_MAP     KEY_SET_INTERNAL  avgt   10      0.016 ±    0.057    B/op
MapIterationBenchmark.run:·gc.count                                         ENUM_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                   ENUM_MAP     KEY_SET_EXTERNAL  avgt   10  10253.559 ±  217.026   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                    ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                               ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      0.017 ±    0.060    B/op
MapIterationBenchmark.run:·gc.count                                         ENUM_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                          IDENTITY_HASH_MAP             INTERNAL  avgt   10  10152.744 ±  258.345   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                           IDENTITY_HASH_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                      IDENTITY_HASH_MAP             INTERNAL  avgt   10      0.017 ±    0.059    B/op
MapIterationBenchmark.run:·gc.count                                IDENTITY_HASH_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                          IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10  16182.255 ±  522.602   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                           IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10    243.159 ±    7.999  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                      IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10   6192.027 ±    0.094    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                  IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10    249.456 ±   69.690  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm             IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10   6368.248 ± 1890.876    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space              IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.006 ±    0.015  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm         IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.156 ±    0.379    B/op
MapIterationBenchmark.run:·gc.count                                IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10     27.000             counts
MapIterationBenchmark.run:·gc.time                                 IDENTITY_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10     99.000                 ms
MapIterationBenchmark.run                                          IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10  16162.309 ±  592.701   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                           IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10    243.326 ±    8.945  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                      IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10   6192.027 ±    0.098    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                  IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10    242.166 ±   70.599  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm             IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10   6170.989 ± 1863.629    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space              IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.010 ±    0.017  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm         IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.263 ±    0.419    B/op
MapIterationBenchmark.run:·gc.count                                IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10     24.000             counts
MapIterationBenchmark.run:·gc.time                                 IDENTITY_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10    105.000                 ms
MapIterationBenchmark.run                                          IDENTITY_HASH_MAP     KEY_SET_INTERNAL  avgt   10  15497.940 ± 1252.988   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                           IDENTITY_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                      IDENTITY_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.026 ±    0.095    B/op
MapIterationBenchmark.run:·gc.count                                IDENTITY_HASH_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                          IDENTITY_HASH_MAP     KEY_SET_EXTERNAL  avgt   10  15209.847 ±  429.003   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                           IDENTITY_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                      IDENTITY_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.025 ±    0.088    B/op
MapIterationBenchmark.run:·gc.count                                IDENTITY_HASH_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                              WEAK_HASH_MAP             INTERNAL  avgt   10  11409.505 ±  648.471   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               WEAK_HASH_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          WEAK_HASH_MAP             INTERNAL  avgt   10      0.019 ±    0.069    B/op
MapIterationBenchmark.run:·gc.count                                    WEAK_HASH_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                              WEAK_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10  11182.011 ±  501.585   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               WEAK_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          WEAK_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.018 ±    0.063    B/op
MapIterationBenchmark.run:·gc.count                                    WEAK_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                              WEAK_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10  13217.515 ±  571.822   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               WEAK_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          WEAK_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.022 ±    0.076    B/op
MapIterationBenchmark.run:·gc.count                                    WEAK_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                              WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10  20463.753 ±  851.819   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10      2.235 ±    0.094  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10     72.033 ±    0.117    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10      2.383 ±    5.801  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10     75.961 ±  184.936    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.002 ±    0.010  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.066 ±    0.317    B/op
MapIterationBenchmark.run:·gc.count                                    WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10      3.000             counts
MapIterationBenchmark.run:·gc.time                                     WEAK_HASH_MAP     KEY_SET_INTERNAL  avgt   10     21.000                 ms
MapIterationBenchmark.run                                              WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10  19600.701 ± 1580.130   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      1.556 ±    0.117  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10     48.032 ±    0.110    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      1.577 ±    5.027  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10     48.975 ±  156.151    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.005  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.031 ±    0.149    B/op
MapIterationBenchmark.run:·gc.count                                    WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      2.000             counts
MapIterationBenchmark.run:·gc.time                                     WEAK_HASH_MAP     KEY_SET_EXTERNAL  avgt   10     19.000                 ms
MapIterationBenchmark.run                                                  HASHTABLE             INTERNAL  avgt   10  10693.475 ±  718.583   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                   HASHTABLE             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                              HASHTABLE             INTERNAL  avgt   10      0.017 ±    0.059    B/op
MapIterationBenchmark.run:·gc.count                                        HASHTABLE             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                  HASHTABLE   ENTRY_SET_INTERNAL  avgt   10  11446.926 ±  329.918   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                   HASHTABLE   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                              HASHTABLE   ENTRY_SET_INTERNAL  avgt   10      0.019 ±    0.065    B/op
MapIterationBenchmark.run:·gc.count                                        HASHTABLE   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                  HASHTABLE   ENTRY_SET_EXTERNAL  avgt   10  11456.207 ±  364.114   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                   HASHTABLE   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                              HASHTABLE   ENTRY_SET_EXTERNAL  avgt   10      0.019 ±    0.065    B/op
MapIterationBenchmark.run:·gc.count                                        HASHTABLE   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                                  HASHTABLE     KEY_SET_INTERNAL  avgt   10  27074.044 ± 1388.277   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                   HASHTABLE     KEY_SET_INTERNAL  avgt   10      0.564 ±    0.026  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                              HASHTABLE     KEY_SET_INTERNAL  avgt   10     24.047 ±    0.170    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                          HASHTABLE     KEY_SET_INTERNAL  avgt   10      0.795 ±    3.800  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                     HASHTABLE     KEY_SET_INTERNAL  avgt   10     35.086 ±  167.743    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                      HASHTABLE     KEY_SET_INTERNAL  avgt   10      0.025 ±    0.122  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm                 HASHTABLE     KEY_SET_INTERNAL  avgt   10      1.124 ±    5.375    B/op
MapIterationBenchmark.run:·gc.count                                        HASHTABLE     KEY_SET_INTERNAL  avgt   10      1.000             counts
MapIterationBenchmark.run:·gc.time                                         HASHTABLE     KEY_SET_INTERNAL  avgt   10      9.000                 ms
MapIterationBenchmark.run                                                  HASHTABLE     KEY_SET_EXTERNAL  avgt   10  30741.399 ± 2900.962   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                                   HASHTABLE     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                              HASHTABLE     KEY_SET_EXTERNAL  avgt   10      0.052 ±    0.183    B/op
MapIterationBenchmark.run:·gc.count                                        HASHTABLE     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                        CONCURRENT_HASH_MAP             INTERNAL  avgt   10  14988.014 ±  561.964   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                         CONCURRENT_HASH_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                    CONCURRENT_HASH_MAP             INTERNAL  avgt   10      0.024 ±    0.085    B/op
MapIterationBenchmark.run:·gc.count                              CONCURRENT_HASH_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                        CONCURRENT_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10  16742.816 ±  923.189   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                         CONCURRENT_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                    CONCURRENT_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10      0.027 ±    0.094    B/op
MapIterationBenchmark.run:·gc.count                              CONCURRENT_HASH_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                        CONCURRENT_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10  17510.302 ±  422.373   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                         CONCURRENT_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                    CONCURRENT_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.029 ±    0.101    B/op
MapIterationBenchmark.run:·gc.count                              CONCURRENT_HASH_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                        CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10  25773.569 ± 1421.628   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                         CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.592 ±    0.030  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                    CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10     24.043 ±    0.155    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.796 ±    3.806  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm           CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10     31.864 ±  152.341    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space            CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.023 ±    0.110  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm       CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      0.918 ±    4.389    B/op
MapIterationBenchmark.run:·gc.count                              CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      1.000             counts
MapIterationBenchmark.run:·gc.time                               CONCURRENT_HASH_MAP     KEY_SET_INTERNAL  avgt   10      9.000                 ms
MapIterationBenchmark.run                                        CONCURRENT_HASH_MAP     KEY_SET_EXTERNAL  avgt   10  28292.177 ± 2722.281   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                         CONCURRENT_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                    CONCURRENT_HASH_MAP     KEY_SET_EXTERNAL  avgt   10      0.046 ±    0.160    B/op
MapIterationBenchmark.run:·gc.count                              CONCURRENT_HASH_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                   CONCURRENT_SKIP_LIST_MAP             INTERNAL  avgt   10   6654.864 ± 1530.516   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                    CONCURRENT_SKIP_LIST_MAP             INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm               CONCURRENT_SKIP_LIST_MAP             INTERNAL  avgt   10      0.010 ±    0.036    B/op
MapIterationBenchmark.run:·gc.count                         CONCURRENT_SKIP_LIST_MAP             INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                   CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_INTERNAL  avgt   10   8407.296 ±  138.736   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                    CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm               CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_INTERNAL  avgt   10      0.014 ±    0.048    B/op
MapIterationBenchmark.run:·gc.count                         CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                   CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_EXTERNAL  avgt   10   6303.228 ±  482.487   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                    CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm               CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.011 ±    0.041    B/op
MapIterationBenchmark.run:·gc.count                         CONCURRENT_SKIP_LIST_MAP   ENTRY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                   CONCURRENT_SKIP_LIST_MAP     KEY_SET_INTERNAL  avgt   10  50352.528 ± 3728.041   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                    CONCURRENT_SKIP_LIST_MAP     KEY_SET_INTERNAL  avgt   10      0.304 ±    0.022  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm               CONCURRENT_SKIP_LIST_MAP     KEY_SET_INTERNAL  avgt   10     24.081 ±    0.284    B/op
MapIterationBenchmark.run:·gc.count                         CONCURRENT_SKIP_LIST_MAP     KEY_SET_INTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                   CONCURRENT_SKIP_LIST_MAP     KEY_SET_EXTERNAL  avgt   10  50941.945 ± 4364.792   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                    CONCURRENT_SKIP_LIST_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.004  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm               CONCURRENT_SKIP_LIST_MAP     KEY_SET_EXTERNAL  avgt   10      0.087 ±    0.310    B/op
MapIterationBenchmark.run:·gc.count                         CONCURRENT_SKIP_LIST_MAP     KEY_SET_EXTERNAL  avgt   10        ≈ 0             counts
MapIterationBenchmark.run                                              IMMUTABLE_MAP             INTERNAL  avgt   10   8080.649 ±  349.989   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               IMMUTABLE_MAP             INTERNAL  avgt   10      2.516 ±    0.106  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          IMMUTABLE_MAP             INTERNAL  avgt   10     32.013 ±    0.046    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      IMMUTABLE_MAP             INTERNAL  avgt   10      2.385 ±    5.807  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 IMMUTABLE_MAP             INTERNAL  avgt   10     30.369 ±   73.941    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  IMMUTABLE_MAP             INTERNAL  avgt   10      0.002 ±    0.010  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             IMMUTABLE_MAP             INTERNAL  avgt   10      0.026 ±    0.127    B/op
MapIterationBenchmark.run:·gc.count                                    IMMUTABLE_MAP             INTERNAL  avgt   10      3.000             counts
MapIterationBenchmark.run:·gc.time                                     IMMUTABLE_MAP             INTERNAL  avgt   10     31.000                 ms
MapIterationBenchmark.run                                              IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10   8174.270 ±  442.575   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10      2.487 ±    0.133  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10     32.013 ±    0.046    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10      2.388 ±    5.813  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10     30.870 ±   75.201    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10      0.001 ±    0.005  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10      0.013 ±    0.064    B/op
MapIterationBenchmark.run:·gc.count                                    IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10      3.000             counts
MapIterationBenchmark.run:·gc.time                                     IMMUTABLE_MAP   ENTRY_SET_INTERNAL  avgt   10     21.000                 ms
MapIterationBenchmark.run                                              IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10   8112.449 ±  498.782   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10      2.504 ±    0.165  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10     32.013 ±    0.046    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10      2.390 ±    5.818  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10     30.547 ±   74.367    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10     ≈ 10⁻⁶             MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10     ≈ 10⁻⁵               B/op
MapIterationBenchmark.run:·gc.count                                    IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10      3.000             counts
MapIterationBenchmark.run:·gc.time                                     IMMUTABLE_MAP   ENTRY_SET_EXTERNAL  avgt   10     31.000                 ms
MapIterationBenchmark.run                                              IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10  15729.287 ± 1006.059   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10      0.970 ±    0.057  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10     24.026 ±    0.090    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10      0.797 ±    3.811  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10     19.849 ±   94.897    B/op
MapIterationBenchmark.run:·gc.count                                    IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10      1.000             counts
MapIterationBenchmark.run:·gc.time                                     IMMUTABLE_MAP     KEY_SET_INTERNAL  avgt   10     14.000                 ms
MapIterationBenchmark.run                                              IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10  15503.501 ± 1037.183   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                               IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10      0.985 ±    0.063  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                          IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10     24.025 ±    0.086    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                      IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10      1.590 ±    5.069  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm                 IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10     39.067 ±  124.535    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space                  IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10      0.026 ±    0.124  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm             IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10      0.645 ±    3.084    B/op
MapIterationBenchmark.run:·gc.count                                    IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10      2.000             counts
MapIterationBenchmark.run:·gc.time                                     IMMUTABLE_MAP     KEY_SET_EXTERNAL  avgt   10     24.000                 ms
MapIterationBenchmark.run                                         IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10  14603.706 ±  966.053   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                          IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10    268.775 ±   17.943  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                     IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10   6176.024 ±    0.084    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                 IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10    264.416 ±   85.300  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm            IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10   6048.761 ± 1719.322    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space             IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10      0.010 ±    0.022  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm        IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10      0.236 ±    0.497    B/op
MapIterationBenchmark.run:·gc.count                               IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10     30.000             counts
MapIterationBenchmark.run:·gc.time                                IMMUTABLE_ENUM_MAP             INTERNAL  avgt   10    108.000                 ms
MapIterationBenchmark.run                                         IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10  15971.929 ±  871.980   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                          IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    245.442 ±   13.929  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                     IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10   6176.027 ±    0.096    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                 IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    242.006 ±   67.919  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm            IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10   6095.667 ± 1726.601    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space             IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10      0.008 ±    0.016  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm        IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10      0.206 ±    0.402    B/op
MapIterationBenchmark.run:·gc.count                               IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10     24.000             counts
MapIterationBenchmark.run:·gc.time                                IMMUTABLE_ENUM_MAP   ENTRY_SET_INTERNAL  avgt   10    121.000                 ms
MapIterationBenchmark.run                                         IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10  15058.430 ±  940.064   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                          IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10    260.846 ±   15.983  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                     IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10   6176.025 ±    0.091    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                 IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10    256.681 ±   67.355  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm            IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10   6081.423 ± 1601.333    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space             IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.010 ±    0.017  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm        IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10      0.241 ±    0.385    B/op
MapIterationBenchmark.run:·gc.count                               IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10     26.000             counts
MapIterationBenchmark.run:·gc.time                                IMMUTABLE_ENUM_MAP   ENTRY_SET_EXTERNAL  avgt   10     93.000                 ms
MapIterationBenchmark.run                                         IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10  10418.568 ±  851.556   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                          IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10      1.955 ±    0.147  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                     IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10     32.017 ±    0.058    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                 IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10      1.591 ±    5.073  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm            IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10     25.998 ±   82.869    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space             IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10      0.001 ±    0.005  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm        IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10      0.017 ±    0.080    B/op
MapIterationBenchmark.run:·gc.count                               IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10      2.000             counts
MapIterationBenchmark.run:·gc.time                                IMMUTABLE_ENUM_MAP     KEY_SET_INTERNAL  avgt   10     19.000                 ms
MapIterationBenchmark.run                                         IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10  10339.544 ±  572.991   ns/op
MapIterationBenchmark.run:·gc.alloc.rate                          IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      1.965 ±    0.105  MB/sec
MapIterationBenchmark.run:·gc.alloc.rate.norm                     IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10     32.017 ±    0.058    B/op
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space                 IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      1.592 ±    5.075  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Eden_Space.norm            IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10     25.874 ±   82.467    B/op
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space             IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      0.001 ±    0.005  MB/sec
MapIterationBenchmark.run:·gc.churn.PS_Survivor_Space.norm        IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      0.017 ±    0.081    B/op
MapIterationBenchmark.run:·gc.count                               IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10      2.000             counts
MapIterationBenchmark.run:·gc.time                                IMMUTABLE_ENUM_MAP     KEY_SET_EXTERNAL  avgt   10     17.000                 ms
```
