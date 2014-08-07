## 接口需求文档

> 对于每个需要返回的字段，格式为

> [Out] 类型(字段描述)

> 对于每个需要设置的字段，格式为：

> [In] 类型(字段描述)

+ PS: POST/GET 根据需求而定

+ PPS: 在非网络问题情况下，验证和错误描述字段总是存在

含两类接口需求：

1. 未实现过非安全、稳定、防火防盗版本，需要实现的接口

2. 实现过非安全、稳定、防火防盗版本，需要升级的接口

### 未实现过非安全、稳定、防火防盗版本，需要实现的接口

#### 问题详细 （已完成）

> [In] Int(问题ID)

> [Out] String(问题标题)

> [Out] String(问题正文)

> [Out] Int(问题关注数)

> [Out] 回答列表(

> > Int(ID)
 
> > Int(用户ID)

> > String(用户姓名)

> > Int(赞同的人数)

> > String(回答预览)
 
> )

> [Out] Tag列表(

> > Int(ID)

> > Int(名称)

> )

#### 添加回答 （已完成）

> [in] int(问题id)

> [in] 详细的回答

> [in] 与问题相关的图片

> [out] 成功与否
 
#### 关注该问题的用户列表 (已完成)

> [in] int(问题id)

> [out] 用户id

> [out] 用户名

> [out] 用户一句话签名
 
#### 回答的详细  (已完成)

> [In] Int(ID)

> [Out] Int(用户ID)

> [Out] Int(赞同数)

> [Out] String(正文)

> [Out] Int(评论数)

> [Out] Date(日期) 

#### 回答的评论列表 (已完成)

> [In] Int(回答ID)

> [Out] Int(评论人ID)

> [Out] String(评论人姓名)

> [Out] String(评论正文)

> [Out] Date(日期)

#### 文章的详细 (已完成)

> [in] int(文章的id)

> [out] 文章的信息(

> > 文章的标题及详细信息

> > 点赞的人数

> > 相关的话题

> )

> 功能：

> > 点赞和不赞的功能

> > 收藏的功能

#### 文章的评论列表 (已完成)

>  [in] int(文章的id)

>  [in] int(评论分页页码)

>  [out] 评论(

> > 评论的id

> > 评论用户的用户名

> > 评论用户的用户id

> > 评论用户的头像

> > 发布的时间

> > 点赞和回复的人数

> )

#### 添加文章评论 (已完成)

> [in] 评论的id

> [in] 评论内容

> [in] 成功与否

> 功能：

> > 点赞该评论的功能

> > 回复该评论的功能

#### 发现列表 (已完成)

> [In] Int(页数)

> [Out] Array(

> > Int(问题ID)

> > String(问题标题)

> > Int(回答ID)

> > String(回答预览)

> > Int(回答者UID)

> > URI(回答者头像)

> > Int(顶的个数)

> )


#### 我的动态列表

占位

#### 首页动态列表

占位

#### 图片（已完成）

> [In] Binary(图片)

> [Out] Int(图片ID)

#### 搜索话题

> [In] String(关键词)

> [Out] Array(

> > Int(话题ID)

> > String(话题标题)

> > String(话题描述)

> > URI(话题图片)

> )

#### 提问 （已完成）

> [In] String(标题)

> [In] Array(话题ID)

> [In] Array(图片ID)

> [In] String(问题描述)

> [Out] Int(问题ID)

#### 搜索

占位

#### 话题资料 （已完成）

> [Out] (String)关于话题详情

> [Out] String(关于话题预览)

> [Out] (int)关注的人数

> [Out]  是否已经关注  

 
#### 关注操作、(已完成)

> 实现对一个话题的操作

#### 精华列表 (已完成)

> [In] id （话题ID）

> [Out] int (问题ID)

> [Out] String(问题标题)

> [Out] int (回答者uid)

> [Out] String(回答者头像URL)

> [Out] int (回答id)

> [Out] String(赞的人数)

> [Out] String(回复内容)

#### 话题取消关注操作 （已完成）

> [In] String(uid)

> [In] String(topic_id)

#### 热门话题列表，与我关注的话题列表返回字段相同 （已完成）

> [Out] String(图片url)

> [Out] String(标题)

> [Out] String(描述)

> edit by huangchen

#### 精华详情，点击精华列表的item进入的界面 (已完成)

> [In] id (问题ID)

> [Out] int (问题ID)

> [Out] String(问题标题)

> [Out] uid (回答者头像uid)

> [Out] String(回答者头像url)

> [Out] String(回答者姓名)

> [Out] String(回答者一句话介绍)

> [Out] int (回答ID)

> [Out] String(该回答赞的人数)

> [Out] String(回答详情)

> [Out] Int(评论的个数)

> [Out] 当前用户是否已感谢

> edit by huangchen

#### 实现对问题的关注 （已完成）

> 可以用户获取是否关注了这个问题

> 可以关注和取消关注

#### 问题详细的添加

> 获取当前用户是否关注了这个问题（没有cookie，这个字段返回null）

#### 回答详细的添加

> 获取当前用户是否赞或踩了这个回答（在回答的详细中加一个字段）

> 请添加回答者的信息（id，头像url，用户名，一句话签名）

#### 发布回答评论

#### 对回答评论的回复

#### 对回答踩和赞的操作

#### 发现列表中添加文章的id   http://w.hihwei.com/?/api/explore/

#### 文章详细的添加  http://w.hihwei.com/?/api/article/article/?id=2

> 请在文章详细中添加文章作者的信息（作者id，作者头像url，作者的用户名，作者的一句话签名）

> 获取用户对当前的文章是否赞过

#### 文章的评论列表  http://w.hihwei.com/?/api/article/comment/?id=2

> 添加评论是否被用户赞过
