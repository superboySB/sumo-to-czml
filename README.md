# 复现笔记
## 安装
为了方便起见，先安装docker镜像跑跑试试看，一般为了避免和很多其他的应用冲突，会有一个`-p 80:8080`的映射，并且80是可以改的
```sh
docker run -itd --rm --name 3dwebmap-container -p 80:8000 tumgis/3dcitydb-web-map:latest
```
（可选）本机端口转发
```sh
ssh -L 80:localhost:80 -p 17004 ps@36.189.234.178
```
本机访问
```sh
http://localhost:80
```

## 参考资料
- https://www.youtube.com/watch?v=GDf7U8vgyzc
- https://isprs-annals.copernicus.org/articles/X-4-W2-2022/29/2022/isprs-annals-X-4-W2-2022-29-2022.pdf