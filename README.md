# uploader
#### 文件上传组件
#### 依赖jquery或者zepto（由于需要操作dom元素）
#### 兼容性：现代浏览器（需要支持formData）
#Demo
``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Uploader</title>
    <style>
        #upload {
            padding: 20px;
        }
        .cus-class1 {
            display: inline-block;
        }
    </style>
</head>
<body>
<div class="wrap">
    <button id="upload">upload</button>
</div>
<button id="click">销毁实例</button>
<!--如果需要使用loading功能，需要引入该样式文件，反之不需要引入-->
<link rel="stylesheet" href="uploader.css">
<script src="https://cdn.bootcss.com/zepto/1.1.7/zepto.min.js"></script>
<!--依赖jquery或者zepto-->
<script src="uploader.js"></script>
<script>
    // 创建实例
    var uploader = new Uploader({
        id: 'upload',
        action: 'https://www.easy-mock.com/mock/5b2c976f96a0217456c95ecc/example/upload',
        multiple: false,
        loading: true,
        classNames: ['cus-class1', 'cus-class2'],
        headers: {},
        data: {},
        accept: 'image/*',
        onStart: function () {
            // 开始上传的回调
            console.log('start')
        },
        onProgress: function () {
            // 进度的回调
            console.log('onProgress')
        },
        onSuccess: function (res) {
            // 上传成功的回调
            console.log('onSuccess:', res)
        },
        onError: function (err) {
            // 上传失败的回调
            console.log(err, 'onError')
        }
    })
    // 销毁实例
    $("#click").click(function () {
        uploader.destroy()
    })
</script>
</body>
</html>
```
# 参数说明

| Attribute      |    Description | isRequire  | Type | Default |
| :-------- | :--------| :--: | :--: | :-------- |
| id  | 绑定的dom元素id |  true   | String | - |
| action     |   上传的服务器地址 |  true  | String | - |
| accept      |    上传文件类型限制：\*/\*、image/\*、video/\* | false  | String | \*/* |
| capture      |    系统所捕获的默认设备：1.camera(直接调用相机);2.camcorder(直接调用摄像) | false | String | - |
| maxSize      |    文件大小上限 | false  | Number | 500 * 1024 |
| loading      |    是否展示上传菊花图 | false  | Boolean | - |
| classNames      |    组件外层可以自定义的类名 | false  | Array | [ ] |
| multiple      |    文件是否支持多选， multiple为true后，capture就没啥用了 | false | Boolean | false |
| headers |    设置请求头 | false | Object   | {} |
| data      |    设置请求体参数 | false | Object | - |
| name  |    上传的文件的名称 | false | String | "file" |
| onProgress |    上传进度的回调 | false | Function | function(){} |
| onSuccess  |    上传成功的回调 | false | Function | function(){} |
| onError  |    上传失败的回调 | false | Function | function(){} |


| Item      |    Value | Qty  |
| :-------- | --------:| :--: |
| Computer  | 1600 USD |  5   |
| Phone     |   12 USD |  12  |
| Pipe      |    1 USD | 234  |


