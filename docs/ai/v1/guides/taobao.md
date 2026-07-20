# 淘宝

淘宝商品搜索与详情采集

- 平台 ID: `taobao`
- 分类: 国内电商
- 能力数量: 6

## 能力

- `item_search`: 商品搜索。按关键词搜索淘宝商品列表
- `item_search_tmall`: 天猫商品搜索。按关键词搜索天猫商品列表
- `item_search_shop`: 店铺商品。按店铺ID/卖家ID获取店铺全部商品
- `item_get`: 商品详情。按商品ID获取详情，自动写入商品主表+SKU表
- `item_comment`: 商品评论。采集淘宝商品评论与追评（评论区）
- `review_show`: 买家秀。采集淘宝买家秀(review show)与追评数据

具体输入参数、分页、字段和去重规则以同平台 JSON 能力包为准。
