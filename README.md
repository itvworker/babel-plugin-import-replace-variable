# babel-plugin-import-replace-variable
此插件主要作用是替换import的路径, 环境的主要是 process.env.NODE_ENV值



```javascript 1.8
import url from 'js/{key}'
import 'js/{key}'

//如果使用案例下面的配置，生产环境将输入
import url from 'js/api.pro'
import 'js/api.pro'
//开发环境将是
import url from 'js/api.dev'
import 'js/api.dev'
```

###使用
```javascript 1.8
{
    "presets": [
        ["@babel/preset-env", {
            "modules": false,
            "targets": {
                "browsers": ["> 1%", "last 10 versions", "not ie <= 8"]
            }
        }]
    ],
    "plugins": [
        //...
        ["babel-plugin-import-replace-variable",{
            production: {
                key:"api.pro"
            },
            development: {
                key:"api.dev"
            }
        }]
    ]
}
```
