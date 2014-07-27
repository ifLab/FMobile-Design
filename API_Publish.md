#发布相关接口

> 基于： http://w.hihwei.com/?/

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

> URL：api/publish/publish_question/

> HTTP请求方式

- POST

> Header

- COOKIE

> 请求参数：

- question_content (问题标题，note:不是内容，人家就这样设计的，别怨写接口的人，其实他也不能理解)

- question_detail (问题详情，即正文内容)

- attach_access_key (可选，如果传了附件的话，会有这个)

- topics (话题，数组形式)

> 返回结果：

- question_id （问题ID)

> 可能返回的错误信息：

- 你没有权限发布问题 (没有cookie信息，就会有这种结果)

- 请输入问题标题

- 问题标题字数不得少于 5 个字

- 你所在的用户组不允许发布站外链接

- 请为问题添加话题
