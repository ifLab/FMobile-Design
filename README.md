FMobile-Design
==============

API List:

http://w.hihwei.com/api/

补充说明：https://github.com/ifLab/FMobile-Design/blob/master/Supplement.md

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

##用户注册

> URL：register.php

> HTTP请求方式：POST

> 请求参数：user_name (string) password (string) email (string)

> 返回结果：

> > uid 用户编号

> 可能返回的错误原因：

> > user_name already exists 用户名已存在

> > email already exists 邮箱已存在

> > Invalid Parameters 参数无效

> > Insert Failed 数据库插入失败（数据库问题）

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




