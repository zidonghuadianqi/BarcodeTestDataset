# BarcodeTestDataset
Barcode test dataset for repo:https://github.com/SUSTech-OpenCV/Barcode

Most of images come from http://artelab.dista.uninsubria.it/downloads/datasets/barcode/medium_barcode_1d/medium_barcode_1d.html
# 通过率测试说明

## 运行测试

在test模块下的`integration_testing`是通过率测试，会比较本次样例通过率和上一次通过率(测试的接口是detectAndDecode)，请保证每次commit前通过此测试。tips：最好用release版本，不然太多图了。宁可Error也不要错读。

## 添加新的测试样例

**确保在没有更改代码的情况下添加新的测试样例，否则无法确认是测试样例改变的通过率还是代码改变的**

添加后缀为.jpg或.png的图片在`test/data/integration_test_data/`文件夹下，并更新result.csv文件，加入对应的结果(格式：[文件名],[结果])

```
1.jpg,6921168509256
2.jpg,6922255451427
3.jpg,6921168509256
4.jpg,6921168509256
5.jpg,6921168509256
```

最后删除correctness.txt文件重新运行一次`integration_testing`

预期结果

```
wrong case:4.jpg, wrong result:0921768509256, right result:6921168509256
wrong case:6.jpg, wrong result:ERROR, right result:6921168509256
wrong case:7.jpg, wrong result:0921768509256, right result:6921168509256
pass rate: 66.6667%
```



## TODO

增加多结果测试样例
