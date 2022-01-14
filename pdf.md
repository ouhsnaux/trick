# pdf

## 打开方式为预览，而非默认打开

`pdf` 预览而不是直接下载，需要接口返回的流的时候设置。

```xxx
Content-Type: application/pdf

// inline是预览，attachment是下载
Content-disposition: inline 
```

## 文件名

预览文件名为 `url` 最后一级。
