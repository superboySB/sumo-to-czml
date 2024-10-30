# 复现笔记
## 安装
运行相应的SUMO数据转换脚本
```sh
git clone https://github.com/superboySB/sumo-to-czml
cd sumo-to-czml
python sumo2czml_points.py
python sumo2czml_3dmodels.py
```
为了方便起见，先安装docker镜像跑跑试试看，一般为了避免和很多其他的应用冲突，会有一个`-p 80:8080`的映射，并且80是可以改的
```sh
docker run -itd --rm --runtime nvidia --name 3dwebmap-container -v /mnt/md0/sumo-to-czml/data:/var/www/data -p 80:8000 tumgis/3dcitydb-web-map:alpine-v2.0.0
```
自带的token为(最好换成自己的)
```js
Cesium.Ion.defaultAccessToken = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiJkNGVkNjUzNy1kZTliLTRmZDgtYTg2Mi1jYTE0NjkwNDg4NTMiLCJpZCI6NjE5MDEsImlhdCI6MTYyNjQ0ODc2M30.eQkSWPaD_VAKmlq1ne02DfpLDW0hGzlYbZysW6si-04';
```
（可选）本机端口转发
```sh
ssh -L 80:localhost:80 -p 17004 ps@36.189.234.178
```
本机访问
```sh
http://localhost:80
```

## 示例项目结构
```
- index.html
- czml_3Dmodels_sample.czml
- czml_points_sample.czml
- 3Dmodels/
    - Cesium_Man.glb
    - CesiumMilkTruck.glb
```
## 参考资料
- https://www.youtube.com/watch?v=GDf7U8vgyzc
- https://isprs-annals.copernicus.org/articles/X-4-W2-2022/29/2022/isprs-annals-X-4-W2-2022-29-2022.pdf