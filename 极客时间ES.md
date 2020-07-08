# 极客时间ES

### 文档的CRUD

Type 名 约定都用_doc

Create --如果Id已经存在 则报错

Index --如果ID不存在,创建新文档

​	  如果Id已经存在,则先删除现有文档 再创建新文档 版本会增加

Update -- 文档必须已经存在 ，更新只会对响应的字段做增量更新

Index：ID存在则覆盖，不存在则创建

```json
PUT myindex/_doc/1
{
  "user":"mike",
  "comment":"You know , for Search"
}
```

CREATE: 如果id已经存在会失败

```json

PUT myindex/_doc/1
{
  "user": "mike",
  "comment": "You know , for Search"
}

POST /myindex/_doc
{
  "user": "mike",
  "comment": "You know , for Search"
}
```

READ

```json
GET myindex/_doc/1
```

Update:局部更新

```json
POST /myindex/_update/1
{
  "doc": {
    "age": 13
  }
}
```

DELETE

```json
DELETE myindex/_doc/SOWZLHMBPdewndXBu7cy
```























