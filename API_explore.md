#发现相关接口

http://w.hihwei.com/?/

##发现（最新，推荐，热门[30天，7天，当天]，等待回复）

> URL：api/explore/   （ http://w.hihwei.com/?/api/explore/ ）

> HTTP请求方式

- GET

> 请求参数：

- per_page (int)  可选，默认10
- page (int)  可选，默认1
- day (int)  可选，默认30
- is_recommend (int)  可选，有1和0两种值，默认0 
- sort_type （string） 可选，有new，hot，unresponsive三种值，默认new    new：最新  hot：热门  unresponsive：等待回复

> 返回的信息：

- 这个请直接看 http://w.hihwei.com/?/api/explore/ 这个页面（装个jsonview一目了然）

- NOTE：通知，我要特别提醒下，这个接口返回的total_rows是当前页的信息总条数，那，你如何知道信息全部加载完了呢，从第一页开始，当你加载第n页的时候，发现它返回的total_rows是0。恭喜你，已全部加载完成！
