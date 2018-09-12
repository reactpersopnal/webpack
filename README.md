# webpack
尝试webpack官网上的全部内容，结合相应项目中的内容进行分析学习
# 当前项目的版本
webpack 4.18.0
添加的版本为webpack 4+ ，还需安装webpack-cli

# initial the project
npm init -y
generate 'package.json'

#master
初始化项目，webpack构建依赖图，bundle解决调用板块之间的依赖关系,在dist文件夹下编译出main.js
配置webpack的配置文件：webpack.config.js

# asset management
管理图片、字体等文件，添加相应的loader(css-loader,file-loader,style-loader,xml-loader,csv-loader)
可以将资源与代码组合在一起，使资源紧密耦合

# output management（feature/output）
无需在index.html中手动引入所有资源;动态添加output的名称-----HtmlWebpackPlugin、、、
Webpack-manifest-plugin生成manifest.json,显示输出管理

# 代码分离(feature/code-spliting)
三种代码分离方式：（1）入口起点entry:入口包含重复模块，重复模块都会被引入到各个bundle
（2）防止重复：CommonsChunkPlugin去重和分离chunk,将公共依赖提取到已有的入口chunk
Error: webpack.optimize.CommonsChunkPlugin has been removed, please use config.optimization.splitChunks instead.
已经使用config.optimization.splitChunks解决
(3)动态导入，通过模块的内联函数调用
使用import

# 缓存(feature/caching)
通过缓存，加快网站加载速度，不更改文件名称，浏览器会默认没有更新
将类似于react的第三方库提取到单独的vendor chunk文件中
修复vensor每次加载后hash改变，因为自身的moduel.id改变，所以文件名中的hash会改变，生产环境推荐HashedModuleIdsPlugins修改这一问题


 