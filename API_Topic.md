#话题相关接口

## 单个话题列表

> URL：topic.php （http://www.example.com/api/topic.php）

> HTTP请求方式

- GET

> 请求参数：

> [In] Int uid （必须）

> [In] Int topic_id （必须）

> [Out] String(图片url) （话题图片路径：http://www.example.com/uploads/topic/）

> [Out] String(标题)

> [Out] String(描述)

> [Out] Int(当前用户是否已关注，关注：1  未关注：0)

## 话题关注，取消关注操作（推荐）

> URL： topic/ajax/focus_topic/  （DEMO：http://www.example.com/?/topic/ajax/focus_topic/?topic_id=17）

> HTTP请求方式

- GET

> Header

- COOKIE

> 请求参数 

- topic_id (话题ID)

- NOTE：不需要传其他参数，如果当前用户已经关注该话题，会取消关注，反之则关注

## 关注或取消关注某个话题操作

> URL：focus_topic.php （http://www.example.com/api/focus_topic.php）

> HTTP请求方式

- POST

> 请求参数：

> [In] Int uid （必须）

> [In] Int topic_id （必须）

> [In] String type （选，如果是取消关注，此值设为 'cancel' ）

> 如果成功，errno为1，不多解释，因“说在前面”有解释
