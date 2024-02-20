

### 晚間
```
use "/Users/chenshiang/Downloads/109年11月行政區電信信令人口統計資料_鄉鎮市區_SHP/109年11月行政區電信信令人口統計資料_鄉鎮市區.dta"

spmap NIGHT_WORK using 109年11月行政區電信信令人口統計資料_鄉鎮市區_shp, id(_ID) clnumber(20) fcolor(Blues2) ocolor(white ..) osize(0.003 ..) title("行政區電信信令人口統計資料 - 晚間", size(*0.8)) subtitle("Taiwan, 109年11月" " ", size(*0.8)) legstyle(3) legend(ring(1) position(3)) legend(title("人口密集度", size(*0.5)) order(2 " 小" 5 "偏小" 10 "中度" 15 "偏高" 20 " 高"))
```

### 日間
```
use "/Users/chenshiang/Downloads/109年11月行政區電信信令人口統計資料_鄉鎮市區_SHP/109年11月行政區電信信令人口統計資料_鄉鎮市區.dta"

spmap DAY_WORK using 109年11月行政區電信信令人口統計資料_鄉鎮市區_shp, id(_ID) clnumber(20) fcolor(Reds2) ocolor(white ..) osize(0.003 ..) title("行政區電信信令人口統計資料 - 日間", size(*0.8)) subtitle("Taiwan, 109年11月" " ", size(*0.8)) legstyle(3) legend(ring(1) position(3)) legend(title("人口密集度", size(*0.5)) order(2 " 小" 5 "偏小" 10 "中度" 15 "偏高" 20 " 高"))
```


