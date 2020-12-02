## 请求过程
预先在建好表，往内存储一条数据
```
{URL: "https://wwww.baidu.com", UserID: "123", Author: "JACK"}
```
查询流程为

`router` -> `api` -> `service` -> `dao`

最终在api层基于 errors.Is 判断根因，转化为业务错误返回。
```
if errors.Is(err,sql.ErrNoRows) {
	c.JSON(404, "can not find this author")
}
```




