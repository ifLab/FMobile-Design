#发布相关接口

##上传附件

> URL：api/publish/attach_upload/

> HTTP请求方式

- GET

> 请求参数：

- id (string) [附件类型，可能的值：questions,article,answer(默认)]

- qqfile (文件域名称)

> 返回结果：

- access_key （待会点发布的时候，这个也要提交的）

- attach_id （这个是供插入在正文里的，如：[attach]9[/attach] ）

- thumb （如果是图片，会返回90*90的缩略图供预览）

> 可能返回的错误信息：

- 请选择要上传的文件

- 文件类型无效

- 文件尺寸过大

- 上传失败, 请与管理员联系

## 发布问题

