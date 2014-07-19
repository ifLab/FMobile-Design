FMobile-Design
==============

API List:

http://w.hihwei.com/?/

##说在前面
> 接口总是会返回三个字段

- rsm (成功时包含返回的数据，失败时此字段为null)
- errno (1:成功 -1:失败)
- err (成功时此字段为null，失败时此字段包含错误原因，可原样输出)

![Image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/success.png)

![Image](https://raw.githubusercontent.com/ifLab/FMobile-Design/master/api/error.png)



##用户注册

> URL：api/account/register_process/

> HTTP请求方式

- POST

> 请求参数：

- user_name (string)
- password (string) 
- email (string)

> 返回结果：

- uid 用户编号

> 可能返回的错误原因：

- 本站目前关闭注册
- 本站只能通过邀请注册
- 本站只能通过微信注册
- 请输入用户名
- 用户名已经存在
- 用户名包含无效字符
- 用户名中包含敏感词或系统保留字
- E-Mail 已经被使用, 或格式不正确
- 密码长度不符合规则

##用户登录


> URL：api/account/login_process/

> HTTP请求方式

- POST

> 请求参数：

- user_name (string) [可以是用户名也可以是邮箱]
- password (string) 

> 返回结果：

- uid 用户编号

> 可能返回的错误原因：

- 请输入正确的帐号或密码
- 抱歉, 你的账号已经被禁止登录


##用户信息
>改：1，头像给MAX 2，增加文章·威望·积分 

> URL：user.php

> HTTP请求方式：GET

> 请求参数：uid (int)

> 返回结果：

> > user_name 用户名

> > avatar_file 头像文件 (头像文件所在文件夹：http://w.hihwei.com/uploads/avatar/)

> > fans_count 粉丝数

> > friend_count 观众数

> > topic_focus_count 关注话题数量

> > agree_count 赞同数量

> > thanks_count 感谢数量

> > question_count  问题数量

> > answer_count 回答数量

> 可能返回的错误原因：

> > User Does Not Exists 用户不存在

> > Invalid Parameters 参数无效

##用户登录

> URL：login.php

> HTTP请求方式：POST

> 请求参数：user_name (string) password (string)

> 返回结果：

> > uid 用户编号

> > email 用户邮箱

> 可能返回的错误原因：

> > user_name error 用户名不存在

> > password error 密码错误

> > Invalid Parameters 参数无效



##职位列表

> URL：job_list.php

> HTTP请求方式：GET

> 返回结果：

> > id 职位编号

> > job_name 职位名称

> 可能返回的错误原因：

> > Select Failed 数据库读取失败（数据库问题）

##个人资料修改

> URL：profile_setting.php

> HTTP请求方式：POST

> 必填请求参数：uid(int) 

> 选填请求参数：user_name (string) sex (tinyint，1：男  2：女  3：保密)  signature (string，个人签名[简介])  job_id(int) birthday(int，Unix 时间戳)

> 返回结果：

> > uid 用户编号

> 可能返回的错误原因：

> > user_name already exists 用户名已存在

> > Invalid Parameters 参数无效

##用户头像修改

> URL：http://w.hihwei.com/?/account/api/avatar_upload/  （特殊API，不在通用API路径下，实际部署时应该不一样，建议在配置文件中单独设置）

> HTTP请求方式：POST

> 必填请求参数：uid(int)  user_avatar(图片文件域)

> 返回结果：

> > avatar_file 头像文件 (头像文件所在文件夹：http://w.hihwei.com/uploads/avatar/)

> 可能返回的错误原因：

> > Invalid Parameters 参数无效

> > Invalid Filetype 文件类型无效

> > Invalid Filesize 文件尺寸过大

> > Upload Failed 上传失败（服务器问题）




