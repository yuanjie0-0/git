### mockjs 初级使用指南

> mockjs 是个模拟的 api 的 库，可以根据我们配置返回我们想要的数据，不需要真的实现后台API调用。



##### 如何集成到 vue 

1. npm install mockjs

2. 新建 mock.js

3. 在 mockjs 中写如下的数据就好

   ```javascript
   // 引入 mockjs
   import Mock from 'mockjs'
   var Random = Mock.Random
   
   // 使用 mockjs 模拟数据
   Mock.mock('/api/data', 'get', {
     name: Random.name(),
     'total_number|1-1000000': 1,
     'updata_number|1-1000000': 1,
     //   updata_time: Random.date(),
     updata_time: '2019-12-10',
     //   next_updata_time: Random.date(),
     next_updata_time: '2019-12-25',
     //   remark: Random.cparagraph()
     remark: Random.csentence()
   })
   
   Mock.mock('/api/data', 'post', function (data) {
     console.log(data)
     console.log(data.body)
     return {
       name: 'yuanjie'
     }
   })
   ```

4. 在 main.js 中引入 mock.js 

   >  require(mock.js)
   
 5. axios 请求（'/api/data'）