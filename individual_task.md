# Індивідуальне завдання

## Набір данних
Набір данних складається з денних логів трафіку в Чікаго.

З даного набору даних можна дізнатися багато цікавої інформації: регіонів з найвищою щільністю трафіку, сезонності та ін., яку пізніше можна використати для моделювання нової інфраструктури, або планування масових заходів.


## Написати R script для завантаження даних в R.

```r
f <- read.csv('ind.csv');
f
```

```
##        ID Traffic.Volume.Count.Location..Address
## 1       2                              1708 West
## 2       3                              1275 West
## 3       5                               920 West
## 4       6                               758 West
## 5       7                               240 East
## 6       9                              2050 East
## 7      10                             8539 South
## 8      11                             8933 South
## 9      12                             9379 South
## 10     13                             9730 South
## 11     14                             4107 South
## 12     15                             4750 South
## 13     16                             5325 South
## 14     17                             6144 South
## 15     18                             6533 South
## 16     19                             6820 South
## 17     20                             7346 South
## 18     21                             8800 South
## 19     23                            10101 South
## 20     24                             1603 South
## 21     25                             1959 South
## 22     26                             2259 South
## 23     27                             2566 South
## 24     28                             3460 South
## 25     29                             3630 South
## 26     31                             4936 South
## 27     32                             5929 South
## 28     33                             6755 South
## 29     34                             7509 South
## 30     36                             3030 South
## 31     37                             3748 South
## 32     38                             4358 South
## 33     39                             5450 South
## 34     41                             7718 South
## 35     42                             9243 South
## 36     43                            10326 South
## 37     44                             7669 South
## 38     45                             7952 South
## 39     47                             1407 South
## 40     48                             1933 South
## 41     52                             3420 South
## 42     53                             3654 South
## 43     55                             5848 South
## 44     56                            10320 South
## 45     57                             6602 South
## 46     58                             6841 South
## 47     60                             7335 South
## 48     61                             8127 South
## 49     62                             8645 South
## 50     63                             8547 South
## 51     64                             9633 South
## 52     65                             7345 South
## 53     66                             2350 South
## 54     67                             5424 South
## 55     68                             1255 South
## 56     69                             2317 South
## 57     70                             2950 South
## 58     71                             3311 South
## 59     72                             3721 South
## 60     73                             4563 South
## 61     74                             5352 South
## 62     75                             9642 South
## 63     77                             6848 South
## 64     78                             7732 South
## 65     79                              2425 East
## 66     81                             1420 South
## 67     82                             3333 South
## 68     83                             4605 South
## 69     84                             5625 South
## 70     85                             6416 South
## 71     86                             7539 South
## 72     87                             8149 South
## 73     88                             9124 South
## 74     89                             9940 South
## 75     90                             2130 South
## 76     91                             6629 South
## 77     92                             9532 South
## 78     93                             3430 South
## 79     94                             2140 South
## 80     95                             4709 South
## 81     96                             2345 South
## 82     97                             3247 South
## 83     98                              320 South
## 84     99                              711 South
## 85    100                             1447 South
## 86    103                             6154 South
## 87    104                             6480 South
## 88    105                             7132 South
## 89    106                             7500 South
## 90    107                             8140 South
## 91    108                             8822 South
## 92    109                              719 South
## 93    110                              996 South
## 94    111                             1515 South
## 95    112                             1918 South
## 96    113                             2123 South
## 97    114                              700 South
## 98    115                             1302 South
## 99    116                             3541 South
## 100   117                             5348 South
## 101   118                             6020 South
## 102   119                             6722 South
## 103   120                             7328 South
## 104   121                             8728 South
## 105   122                             9550 South
## 106   124                             7925 South
## 107   125                             8940 South
## 108   126                             9520 South
## 109   127                            10122 South
## 110   129                            10748 South
## 111   130                              721 South
##                           Street Date.of.Count
## 1                    71st Street    03/09/2006
## 2                    71st Street    02/28/2006
## 3                    71st Street    02/28/2006
## 4                    71st Street    02/28/2006
## 5                        71st St    02/28/2006
## 6                        71st St    03/09/2006
## 7                 Commercial Ave    03/07/2006
## 8                 Commercial Ave    03/07/2006
## 9                 Commercial Ave    03/07/2006
## 10                Commercial Ave    03/07/2006
## 11             Cottage Grove Ave    03/30/2006
## 12             Cottage Grove Ave    03/01/2006
## 13             Cottage Grove Ave    02/01/2006
## 14             Cottage Grove Ave    03/01/2006
## 15             Cottage Grove Ave    03/01/2006
## 16             Cottage Grove Ave    02/01/2006
## 17             Cottage Grove Ave    03/01/2006
## 18             Cottage Grove Ave    03/01/2006
## 19             Cottage Grove Ave    03/02/2006
## 20                     Damen Ave    03/02/2006
## 21                     Damen Ave    03/02/2006
## 22                     Damen Ave    03/02/2006
## 23                     Damen Ave    05/09/2006
## 24                     Damen Ave    03/02/2006
## 25                     Damen Ave    03/01/2006
## 26                     Damen Ave    03/09/2006
## 27                     Damen Ave    03/09/2006
## 28                     Damen Ave    03/02/2006
## 29                     Damen Ave    03/02/2006
## 30   Dr Martin Luther King Jr Dr    03/14/2006
## 31   Dr Martin Luther King Jr Dr    03/02/2006
## 32   Dr Martin Luther King Jr Dr    03/02/2006
## 33   Dr Martin Luther King Jr Dr    02/28/2006
## 34   Dr Martin Luther King Jr Dr    02/28/2006
## 35   Dr Martin Luther King Jr Dr    02/28/2006
## 36   Dr Martin Luther King Jr Dr    02/28/2006
## 37                  Exchange Ave    03/07/2006
## 38                  Exchange Ave    03/07/2006
## 39                   Indiana Ave    05/02/2006
## 40                   Indiana Ave    03/02/2006
## 41                   Indiana Ave    05/02/2006
## 42                   Indiana Ave    03/02/2006
## 43                   Indiana Ave    03/02/2006
## 44              Indianapolis Ave    05/11/2006
## 45                  Jeffery Blvd    03/08/2006
## 46                  Jeffery Blvd    05/04/2006
## 47                  Jeffery Blvd    05/04/2006
## 48                  Jeffery Blvd    03/08/2006
## 49                  Jeffery Blvd    05/04/2006
## 50                  Jeffery Blvd    03/29/2006
## 51                   Jeffery Ave    05/04/2006
## 52   Dr Martin Luther King Jr Dr    05/02/2006
## 53   Dr Martin Luther King Jr Dr    05/02/2006
## 54                 Lake Park Ave    03/08/2006
## 55                  Michigan Ave    03/02/2006
## 56                  Michigan Ave    03/02/2006
## 57                  Michigan Ave    03/02/2006
## 58                  Michigan Ave    03/02/2006
## 59                  Michigan Ave    03/02/2006
## 60                  Michigan Ave    03/02/2006
## 61                  Michigan Ave    03/02/2006
## 62                  Michigan Ave    03/15/2006
## 63                South Shore Dr    03/09/2006
## 64                South Shore Dr    03/09/2006
## 65                South Shore Dr    03/09/2006
## 66                      State St    05/02/2006
## 67                      State St    03/07/2006
## 68                      State St    05/02/2006
## 69                      State St    03/07/2006
## 70                      State St    05/02/2006
## 71                      State St    03/28/2006
## 72                      State St    05/02/2006
## 73                      State St    03/08/2006
## 74                      State St    05/02/2006
## 75                 Wentworth Ave    03/07/2006
## 76                 Wentworth Ave    03/07/2006
## 77                 Wentworth Ave    03/08/2006
## 78                    Archer Ave    03/08/2006
## 79                    Archer Ave    03/08/2006
## 80                    Archer Ave    03/08/2006
## 81                    Archer Ave    03/08/2006
## 82                    Archer Ave    03/08/2006
## 83                   Ashland Ave    03/21/2006
## 84                   Ashland Ave    03/21/2006
## 85                   Ashland Ave    03/21/2006
## 86                   Ashland Ave    03/14/2006
## 87                   Ashland Ave    03/21/2006
## 88                   Ashland Ave    03/21/2006
## 89                   Ashland Ave    03/21/2006
## 90                   Ashland Ave    03/14/2006
## 91                   Ashland Ave    03/14/2006
## 92                      Clark St    03/15/2006
## 93                      Clark St    03/22/2006
## 94                      Clark St    03/22/2006
## 95                      Clark St    03/15/2006
## 96                      Clark St    03/15/2006
## 97                    Halsted St    03/21/2006
## 98                    Halsted St    03/21/2006
## 99                    Halsted St    03/21/2006
## 100                   Halsted St    03/15/2006
## 101                   Halsted St    03/21/2006
## 102                   Halsted St    03/21/2006
## 103                   Halsted St    03/21/2006
## 104                   Halsted St    03/21/2006
## 105                   Halsted St    03/21/2006
## 106                Vincennes Ave    03/29/2006
## 107                Vincennes Ave    03/21/2006
## 108                Vincennes Ave    03/21/2006
## 109                Vincennes Ave    03/21/2006
## 110                Vincennes Ave    03/21/2006
## 111                  Western Ave    03/22/2006
##      Total.Passing.Vehicle.Volume
## 1                           14600
## 2                           16500
## 3                           18200
## 4                           21600
## 5                           18300
## 6                            8600
## 7                           10000
## 8                           10500
## 9                           12700
## 10                           9000
## 11                          10800
## 12                          14200
## 13                          13700
## 14                          20900
## 15                          19100
## 16                          21700
## 17                          17800
## 18                          22400
## 19                          12500
## 20                          18800
## 21                          15300
## 22                          14800
## 23                          28000
## 24                           8100
## 25                           7000
## 26                          10900
## 27                          14900
## 28                          16600
## 29                          12300
## 30                          19900
## 31                          15600
## 32                          14500
## 33                          11800
## 34                          16700
## 35                          15500
## 36                          11100
## 37                           8300
## 38                           7400
## 39                           8300
## 40                           6100
## 41                           7400
## 42                           6000
## 43                           4400
## 44                          38500
## 45                          21200
## 46                          23700
## 47                          24300
## 48                          13400
## 49                          19300
## 50                          12400
## 51                           7700
## 52                          18900
## 53                          18100
## 54                          18200
## 55                          20600
## 56                          13000
## 57                          13200
## 58                           8100
## 59                           8000
## 60                           7900
## 61                           7900
## 62                           8100
## 63                          35100
## 64                          16400
## 65                          17300
## 66                          23100
## 67                          10100
## 68                          21500
## 69                          16100
## 70                          19300
## 71                          12500
## 72                           7500
## 73                           4900
## 74                           7300
## 75                           4500
## 76                           7100
## 77                           4900
## 78                          23400
## 79                          11800
## 80                          27800
## 81                          13300
## 82                          15100
## 83                          29300
## 84                          38700
## 85                          38300
## 86                          23500
## 87                          27100
## 88                          35000
## 89                          26300
## 90                          26300
## 91                          27800
## 92                          13600
## 93                          22600
## 94                          23000
## 95                          14800
## 96                          12800
## 97                          15600
## 98                          13400
## 99                          15300
## 100                         15000
## 101                         13200
## 102                         13500
## 103                         16700
## 104                         30900
## 105                         37900
## 106                         21200
## 107                         16300
## 108                         12500
## 109                         13700
## 110                         18000
## 111                         29500
##      Vehicle.Volume.By.Each.Direction.of.Traffic Latitude Longitude
## 1            East Bound: 6900 / West Bound: 7700 41.76488 -87.66663
## 2            East Bound: 7800 / West Bound: 8700 41.76501 -87.65707
## 3            East Bound: 8800 / West Bound: 9400 41.76515 -87.64775
## 4          East Bound: 10400 / West Bound: 11200 41.76520 -87.64437
## 5            East Bound: 9000 / West Bound: 9300 41.76564 -87.61848
## 6            East Bound: 3600 / West Bound: 5000 41.76626 -87.57423
## 7          North Bound: 5000 / South Bound: 5000 41.73984 -87.55148
## 8          North Bound: 4900 / South Bound: 5600 41.73273 -87.55132
## 9          North Bound: 6000 / South Bound: 6700 41.72444 -87.55112
## 10         North Bound: 4000 / South Bound: 5000 41.71818 -87.55102
## 11         North Bound: 5600 / South Bound: 5200 41.82017 -87.60680
## 12         North Bound: 7000 / South Bound: 7200 41.80799 -87.60653
## 13         North Bound: 7200 / South Bound: 6500 41.79788 -87.60630
## 14       North Bound: 10300 / South Bound: 10600 41.78269 -87.60598
## 15         North Bound: 9800 / South Bound: 9300 41.77578 -87.60583
## 16       North Bound: 10300 / South Bound: 11400 41.77069 -87.60571
## 17         North Bound: 8700 / South Bound: 9100 41.76080 -87.60545
## 18       North Bound: 11100 / South Bound: 11300 41.73479 -87.60478
## 19         North Bound: 5800 / South Bound: 6700 41.71092 -87.60573
## 20         North Bound: 9600 / South Bound: 9200 41.85938 -87.67604
## 21         North Bound: 7700 / South Bound: 7600 41.85493 -87.67592
## 22         North Bound: 8000 / South Bound: 6800 41.85039 -87.67579
## 23       North Bound: 13800 / South Bound: 14200 41.84488 -87.67565
## 24         North Bound: 3800 / South Bound: 4300 41.83039 -87.67528
## 25         North Bound: 3200 / South Bound: 3800 41.82762 -87.67521
## 26         North Bound: 5900 / South Bound: 5000 41.80374 -87.67457
## 27         North Bound: 7600 / South Bound: 7300 41.78575 -87.67408
## 28         North Bound: 7900 / South Bound: 8700 41.77041 -87.67367
## 29         North Bound: 5600 / South Bound: 6700 41.75736 -87.67334
## 30        North Bound: 10000 / South Bound: 9900 41.83842 -87.61746
## 31         North Bound: 7300 / South Bound: 8300 41.82598 -87.61704
## 32         North Bound: 6600 / South Bound: 7900 41.81485 -87.61674
## 33         North Bound: 5600 / South Bound: 6200 41.79509 -87.61599
## 34         North Bound: 7900 / South Bound: 8800 41.75419 -87.61503
## 35         North Bound: 7800 / South Bound: 7700 41.72624 -87.61425
## 36         North Bound: 5300 / South Bound: 5800 41.70649 -87.61374
## 37         North Bound: 3900 / South Bound: 4400 41.75580 -87.55646
## 38         North Bound: 3500 / South Bound: 3900 41.75040 -87.55280
## 39         North Bound: 4900 / South Bound: 3400 41.86394 -87.62247
## 40         North Bound: 3800 / South Bound: 2300 41.85566 -87.62228
## 41      North Bound: 7400 / / Oneway North Bound 41.83217 -87.62179
## 42      North Bound: 6000 / / Oneway North Bound 41.82802 -87.62169
## 43      North Bound: 4400 / / Oneway North Bound 41.78778 -87.62067
## 44       North Bound: 19200 / South Bound: 19300 41.70761 -87.52970
## 45       North Bound: 10600 / South Bound: 10600 41.77522 -87.57516
## 46       North Bound: 11300 / South Bound: 12400 41.77038 -87.57641
## 47       North Bound: 11200 / South Bound: 13100 41.76145 -87.57620
## 48         North Bound: 6500 / South Bound: 6900 41.74715 -87.57590
## 49        North Bound: 9300 / South Bound: 10000 41.73790 -87.57571
## 50         North Bound: 5700 / South Bound: 6700 41.73927 -87.57575
## 51         North Bound: 4100 / South Bound: 3600 41.71973 -87.57529
## 52         North Bound: 9400 / South Bound: 9500 41.76069 -87.61517
## 53        North Bound: 10700 / South Bound: 7400 41.84934 -87.61846
## 54         North Bound: 8900 / South Bound: 9300 41.79737 -87.58732
## 55        North Bound: 11200 / South Bound: 9400 41.86592 -87.62412
## 56         North Bound: 5800 / South Bound: 7200 41.85059 -87.62374
## 57         North Bound: 5100 / South Bound: 8100 41.83956 -87.62349
## 58         South Bound: 8100/ Oneway South Bound 41.83437 -87.62332
## 59         South Bound: 8000/ Oneway South Bound 41.82681 -87.62315
## 60         South Bound: 7900/ Oneway South Bound 41.81119 -87.62289
## 61         South Bound: 7900/ Oneway South Bound 41.79665 -87.62252
## 62         North Bound: 3600 / South Bound: 4500 41.71866 -87.62052
## 63       North Bound: 17900 / South Bound: 17200 41.77024 -87.56656
## 64         North Bound: 8100 / South Bound: 8300 41.75631 -87.55270
## 65         North Bound: 8600 / South Bound: 8700 41.76631 -87.56547
## 66        North Bound: 13500 / South Bound: 9600 41.86344 -87.62733
## 67         North Bound: 6700 / South Bound: 3400 41.83366 -87.62647
## 68       North Bound: 11200 / South Bound: 10300 41.81090 -87.62613
## 69         North Bound: 8800 / South Bound: 7300 41.79208 -87.62563
## 70        North Bound: 8800 / South Bound: 10500 41.77707 -87.62526
## 71     North Bound: 12500 / / Oneway North Bound 41.75705 -87.62474
## 72      North Bound: 7500 / / Oneway North Bound 41.74581 -87.62439
## 73      North Bound: 4900 / / Oneway North Bound 41.72828 -87.62391
## 74         North Bound: 4400 / South Bound: 2900 41.71325 -87.62365
## 75         North Bound: 2300 / South Bound: 2200 41.85316 -87.63178
## 76         North Bound: 2800 / South Bound: 4300 41.77365 -87.62999
## 77         North Bound: 2800 / South Bound: 2100 41.72066 -87.62864
## 78       North Bound: 11300 / South Bound: 12100 41.83150 -87.67584
## 79         North Bound: 5200 / South Bound: 6600 41.85355 -87.63339
## 80       North Bound: 13600 / South Bound: 14200 41.80782 -87.71447
## 81         North Bound: 7100 / South Bound: 6200 41.84998 -87.64032
## 82         North Bound: 8200 / South Bound: 6900 41.83511 -87.66995
## 83       North Bound: 15200 / South Bound: 14100 41.87693 -87.66668
## 84       North Bound: 21100 / South Bound: 17600 41.87257 -87.66656
## 85       North Bound: 19800 / South Bound: 18500 41.86187 -87.66626
## 86       North Bound: 11800 / South Bound: 11700 41.78144 -87.66427
## 87       North Bound: 14000 / South Bound: 13100 41.77583 -87.66412
## 88       North Bound: 16500 / South Bound: 18500 41.76396 -87.66375
## 89       North Bound: 12800 / South Bound: 13500 41.75772 -87.66361
## 90       North Bound: 13600 / South Bound: 12700 41.74547 -87.66331
## 91       North Bound: 15200 / South Bound: 12600 41.73329 -87.66299
## 92         North Bound: 6500 / South Bound: 7100 41.87301 -87.63063
## 93       North Bound: 12500 / South Bound: 10100 41.86989 -87.63051
## 94       North Bound: 12700 / South Bound: 10300 41.86148 -87.63026
## 95         North Bound: 8500 / South Bound: 6300 41.85596 -87.63018
## 96         North Bound: 7300 / South Bound: 5500 41.85347 -87.63009
## 97         North Bound: 6700 / South Bound: 8900 41.87346 -87.64709
## 98         North Bound: 5900 / South Bound: 7500 41.86531 -87.64686
## 99         North Bound: 7900 / South Bound: 7400 41.82951 -87.64608
## 100        North Bound: 7700 / South Bound: 7300 41.79647 -87.64521
## 101        North Bound: 6900 / South Bound: 6300 41.78453 -87.64490
## 102        North Bound: 7600 / South Bound: 5900 41.77177 -87.64458
## 103        North Bound: 8800 / South Bound: 7900 41.76068 -87.64430
## 104      North Bound: 16500 / South Bound: 14400 41.73500 -87.64359
## 105      North Bound: 20800 / South Bound: 17100 41.71997 -87.64317
## 106       North Bound: 9700 / South Bound: 11500 41.75002 -87.63442
## 107        North Bound: 8800 / South Bound: 7500 41.73117 -87.64703
## 108        North Bound: 6300 / South Bound: 6200 41.72080 -87.65084
## 109        North Bound: 6400 / South Bound: 7300 41.71070 -87.65457
## 110        North Bound: 8800 / South Bound: 9200 41.69803 -87.65927
## 111      North Bound: 14900 / South Bound: 14600 41.87243 -87.68620
##                     Location
## 1    (41.764877, -87.666635)
## 2    (41.765008, -87.657067)
## 3    (41.765153, -87.647751)
## 4    (41.765204, -87.644371)
## 5    (41.765644, -87.618476)
## 6     (41.76626, -87.574226)
## 7    (41.739836, -87.551476)
## 8     (41.732725, -87.55132)
## 9    (41.724444, -87.551124)
## 10   (41.718183, -87.551016)
## 11   (41.820171, -87.606798)
## 12   (41.807987, -87.606532)
## 13   (41.797881, -87.606302)
## 14    (41.78269, -87.605979)
## 15   (41.775779, -87.605826)
## 16   (41.770685, -87.605711)
## 17   (41.760801, -87.605452)
## 18   (41.734791, -87.604779)
## 19    (41.710922, -87.60573)
## 20   (41.859378, -87.676043)
## 21    (41.854926, -87.67592)
## 22    (41.850395, -87.67579)
## 23   (41.844875, -87.675652)
## 24   (41.830389, -87.675279)
## 25   (41.827625, -87.675208)
## 26   (41.803741, -87.674569)
## 27   (41.785746, -87.674075)
## 28   (41.770409, -87.673671)
## 29   (41.757363, -87.673336)
## 30   (41.838419, -87.617465)
## 31   (41.825982, -87.617039)
## 32   (41.814852, -87.616741)
## 33   (41.795094, -87.615989)
## 34   (41.754187, -87.615027)
## 35   (41.726239, -87.614254)
## 36   (41.706494, -87.613745)
## 37    (41.755798, -87.55646)
## 38       (41.7504, -87.5528)
## 39   (41.863938, -87.622471)
## 40     (41.85566, -87.62228)
## 41   (41.832167, -87.621788)
## 42   (41.828022, -87.621694)
## 43   (41.787779, -87.620665)
## 44   (41.707611, -87.529702)
## 45   (41.775215, -87.575158)
## 46    (41.77038, -87.576414)
## 47   (41.761454, -87.576196)
## 48   (41.747152, -87.575902)
## 49   (41.737902, -87.575714)
## 50   (41.739269, -87.575753)
## 51    (41.719732, -87.57529)
## 52   (41.760689, -87.615174)
## 53   (41.849344, -87.618459)
## 54   (41.797367, -87.587322)
## 55   (41.865924, -87.624115)
## 56   (41.850595, -87.623745)
## 57   (41.839562, -87.623493)
## 58   (41.834369, -87.623323)
## 59   (41.826807, -87.623149)
## 60   (41.811191, -87.622886)
## 61   (41.796652, -87.622518)
## 62   (41.718658, -87.620521)
## 63   (41.770241, -87.566558)
## 64   (41.756313, -87.552698)
## 65   (41.766314, -87.565472)
## 66    (41.863436, -87.62733)
## 67   (41.833661, -87.626468)
## 68   (41.810903, -87.626128)
## 69   (41.792077, -87.625634)
## 70    (41.777072, -87.62526)
## 71   (41.757046, -87.624736)
## 72   (41.745812, -87.624391)
## 73   (41.728281, -87.623913)
## 74   (41.713246, -87.623646)
## 75   (41.853156, -87.631785)
## 76   (41.773651, -87.629987)
## 77   (41.720659, -87.628638)
## 78    (41.831501, -87.67584)
## 79   (41.853553, -87.633392)
## 80   (41.807818, -87.714468)
## 81    (41.849975, -87.64032)
## 82   (41.835106, -87.669954)
## 83   (41.876934, -87.666676)
## 84    (41.872567, -87.66656)
## 85   (41.861874, -87.666256)
## 86   (41.781444, -87.664267)
## 87    (41.775834, -87.66412)
## 88   (41.763965, -87.663752)
## 89   (41.757724, -87.663608)
## 90   (41.745469, -87.663314)
## 91   (41.733288, -87.662994)
## 92   (41.873009, -87.630632)
## 93   (41.869893, -87.630511)
## 94   (41.861478, -87.630255)
## 95   (41.855964, -87.630176)
## 96   (41.853467, -87.630093)
## 97    (41.87346, -87.647091)
## 98   (41.865313, -87.646862)
## 99   (41.829513, -87.646078)
## 100  (41.796466, -87.645213)
## 101   (41.78453, -87.644905)
## 102  (41.771775, -87.644579)
## 103  (41.760683, -87.644298)
## 104  (41.735001, -87.643587)
## 105  (41.719968, -87.643173)
## 106   (41.75002, -87.634415)
## 107  (41.731171, -87.647028)
## 108  (41.720798, -87.650838)
## 109  (41.710702, -87.654574)
## 110   (41.698034, -87.65927)
## 111  (41.872427, -87.686197)
##  [ reached getOption("max.print") -- omitted 1168 rows ]
```
```cmd
```

###Підключимо необхідні бібліотеки

```r
library(ggmap)
library(tidyverse)
library(RColorBrewer)
library(lubridate)
```


###Виведемо самері 

```r
places <- read.csv(file="ind.csv",head=TRUE)
summary(places)
```

```
##        ID         Traffic.Volume.Count.Location..Address
##  Min.   :   1.0   20 West  :   4                        
##  1st Qu.: 348.5   210 South:   4                        
##  Median : 684.0   299 North:   4                        
##  Mean   : 689.9   10 East  :   3                        
##  3rd Qu.:1028.5   120 East :   3                        
##  Max.   :1382.0   700 South:   3                        
##                   (Other)  :1258                        
##           Street        Date.of.Count  Total.Passing.Vehicle.Volume
##  Damen Ave   :  33   03/28/2006:  73   Min.   :   700              
##  Western Ave :  32   10/18/2006:  53   1st Qu.: 11350              
##  Ashland Ave :  31   09/19/2006:  40   Median : 17300              
##  Pulaski Rd  :  28   08/15/2006:  36   Mean   : 19466              
##  Halsted St  :  26   08/22/2006:  34   3rd Qu.: 24200              
##  Michigan Ave:  23   10/11/2006:  34   Max.   :165200              
##  (Other)     :1106   (Other)   :1009                               
##                    Vehicle.Volume.By.Each.Direction.of.Traffic
##  North Bound: 6300 / South Bound: 6200   :   4                
##  East Bound: 3800 / West Bound: 4800     :   3                
##  East Bound: 10400 / West Bound: 10500   :   2                
##  East Bound: 11700 / West Bound: 11300   :   2                
##  East Bound: 14100 / West Bound: 12100   :   2                
##  East Bound: 14300 / / Oneway East Bound :   2                
##  (Other)                                 :1264                
##     Latitude       Longitude                         Location   
##  Min.   :41.65   Min.   :-87.85   (41.828474, -87.65091) :   2  
##  1st Qu.:41.78   1st Qu.:-87.71   (41.87346, -87.647091) :   2  
##  Median :41.87   Median :-87.66   (41.876934, -87.666676):   2  
##  Mean   :41.85   Mean   :-87.67   (41.651861, -87.54501) :   1  
##  3rd Qu.:41.91   3rd Qu.:-87.63   (41.655545, -87.559298):   1  
##  Max.   :42.02   Max.   :-87.53   (41.65732, -87.557177) :   1  
##                                   (Other)                :1270
```
```cmd
```
##№ Підготуємо дати

```r
places$Date.of.Count <- as.factor(places$Date.of.Count)
places$Date.of.Count <-strptime(places$Date.of.Count,format="%m/%d/%Y")
places$Date.of.Count <-as.Date(places$Date.of.Count,format="%m-%Y")

places[, "month"] <- format(places[,"Date.of.Count"], "%m" )

head(places)
```

```
##   ID Traffic.Volume.Count.Location..Address      Street Date.of.Count
## 1  2                              1708 West 71st Street    2006-03-09
## 2  3                              1275 West 71st Street    2006-02-28
## 3  5                               920 West 71st Street    2006-02-28
## 4  6                               758 West 71st Street    2006-02-28
## 5  7                               240 East     71st St    2006-02-28
## 6  9                              2050 East     71st St    2006-03-09
##   Total.Passing.Vehicle.Volume Vehicle.Volume.By.Each.Direction.of.Traffic
## 1                        14600         East Bound: 6900 / West Bound: 7700
## 2                        16500         East Bound: 7800 / West Bound: 8700
## 3                        18200         East Bound: 8800 / West Bound: 9400
## 4                        21600       East Bound: 10400 / West Bound: 11200
## 5                        18300         East Bound: 9000 / West Bound: 9300
## 6                         8600         East Bound: 3600 / West Bound: 5000
##   Latitude Longitude                Location month
## 1 41.76488 -87.66663 (41.764877, -87.666635)    03
## 2 41.76501 -87.65707 (41.765008, -87.657067)    02
## 3 41.76515 -87.64775 (41.765153, -87.647751)    02
## 4 41.76520 -87.64437 (41.765204, -87.644371)    02
## 5 41.76564 -87.61848 (41.765644, -87.618476)    02
## 6 41.76626 -87.57423  (41.76626, -87.574226)    03
```

```cmd
```

###Візуалізуємо по датам

```r
aggr <- aggregate(x = places$Total.Passing.Vehicle.Volume,
                     FUN = sum,
                     by = list(Group.date = places$month))
plot(aggr, type="o", col="blue")
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png)
```cmd
```

###реєструємо АПІ для гугл карт

```r
register_google(key = "AIzaSyBVj1Y8sJgH7rUBkzFqaG5fV3VZV7jfRzc")
```
###Карта

```r
map.chicago <- get_map("Chicago")
```

```
## Source : https://maps.googleapis.com/maps/api/staticmap?center=Chicago&zoom=10&size=640x640&scale=2&maptype=terrain&language=en-EN&key=xxx
```

```
## Source : https://maps.googleapis.com/maps/api/geocode/json?address=Chicago&key=xxx
```

```r
ggmap(map.chicago, zoom = 11) +
geom_point(data = places, aes(x = Longitude, y = Latitude, fill = Total.Passing.Vehicle.Volume), size = 1, shape = 20, inherit.aes = FALSE) + scale_color_gradient(low="blue", high="red")
```

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-7-1.png)
```cmd
```

###Щільність транспорту

```r
ggmap(map.chicago, zoom = 11) +
stat_density_2d(data = places,
                  aes(x = Longitude,
                      y = Latitude,
                      fill = stat(level)),
                  alpha = .1,
                  bins = 25,
                  geom = "polygon") +
  scale_fill_gradientn(colors = brewer.pal(7, "YlOrRd"))
```

![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-8-1.png)
```cmd
```

## Висновки
### 1. Найбільш напруженим сезоном з точки зору трафіку в Чікаго - є осінь.
### 2. Очікуванно центр міста є найбільш загруженим.
### 3. В центрі міста денна кількість транспорту може сягати 165 200 авто, в той час як середня кількість по місту - ~20 000.
