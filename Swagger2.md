#### Swagger2

@ApilmplicitParam中dataType和paramType的区别：

`@ApilmplicitParam(name= "id", value = "用户id", required = true, dataType = "Integer", paramType = "query")`

dataType :代表请求参数类型

paramType: 代表参数应该放在请求的哪个地方

paramType的取值：

- header :放在请求头，请求参数的获取@RequestHeader，such as `X-MyHeader: Value`
- query ：用于请求的参数拼接，请求参数的获取@RequestParam ，such as `/users?role=admin`
- path :  用于restful接口，请求参数的获取：@PathVariable，such as `/users/{id}`
- body : 放在请求体，请求参数的获取：@RequestBody
- form : form表示FormData，其实很常用了，任何@RequestParam注解修饰的字段，都可以用FormData来传，可以说比query更加推荐，但是swagger不用form是因为swagger-ui.html还不能发送formData

