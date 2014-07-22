## 接口需求文档

> 对于每个需要返回的字段，格式为

> [Out] 类型(字段描述)

> 对于每个需要设置的字段，格式为：

> [In] 类型(字段描述)

+ PS: POST/GET 根据需求而定

+ PPS: 在非网络问题情况下，验证和错误描述字段总是存在

含两类接口需求：

1. 未实现过非安全、稳定、防火防盗版本，需要实现的接口

2.  实现过非安全、稳定、防火防盗版本，需要升级的接口

### 未实现过非安全、稳定、防火防盗版本，需要实现的接口

#### 获取我的提问列表

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > String(问题预览)

> > Date(提问时间)

> )

#### 获取我的回复列表

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > String(回复用户头像URI)

> > Int(回复ID)

> > String(回复预览)

> > Int(回复赞同数)

> )

#### 获取我的文章列表

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(文章ID)

> > String(文章标题)

> > String(文章预览)

> > Date(发表日期)

> )

#### 获取我的关注问题列表

> [In] Int(UID)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > Date(提问时间)

> > Int(关注人数)

> > Int(答案数)

> )

#### 发现列表

占位

#### 我的动态列表

占位

#### 首页动态列表

占位

#### 提问

占位

#### 搜索

占位

### 实现过非安全、稳定、防火防盗版本，需要升级的接口

#### 用获取户信息

用于获取并展示个人主页信息

> [In] Int(UID)

> [Out] String(用户头像URI)

> [Out] String(用户名)

> [Out] Int(我的话题数)

> [Out] Int(我关注的人数)

> [Out] Int(关注我的人数)

> [Out] Int(赞同我的次数)

> [Out] Int(感谢我的次数)

> [Out] Int(答案被收藏次数)

> [Out] Int(答案被分享次数)

#### 修改用户信息

用于用户展示信息修改

> [In] Int(UID)

> [In] String(用户名)

> [In] Int(性别ID)

> [In] String(个人简介)

> [In] Int(行业ID)

> [In] Date(生日)

> [Out] Bool(成功／失败)

#### 获取职位列表

用于展示／修改个人从属行业等信息

> [In] Int(页数)

> [Out] Array(

> > Int(职业ID)

> > String(职业名称)

> )

