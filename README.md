FMobile-Design
==============

API List:

http://w.hihwei.com/api/



##用户信息

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



