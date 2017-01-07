以前一直使用wordpress写博客，现在前端流行了，我也玩一下，对比了一下最后选择了hexo.
hexo 是使用node.js 为服务端开发的静态资源框架，所以一定要新安装node.js

我的node.js 版本是7.3.0，系统是windows 7

github url : https://github.com/hexojs/hexo
官网url : https://hexo.io/

一、安装hexo
设置淘宝cnpm
npm install -g cnpm --registry=https://registry.npm.taobao.org

npm install hexo-cli -g #全局安装hexo-cli

1.在d盘下创建目录hexoblog
cd hexoblog
hexo init #初始化博客

2.hexo server #启动服务默认4000端口 

3.新建博文
hexo new "myfirst"
此时在hexoblog/source/_posts/下生成myfirst.md
这时你用IDE打开myfirst.md 自己编写内容就行了。

4.生成静态页面
hexo generate


5.此时访问http://127.0.0.1:4000/ 就可以看到首页了

二、更换主题
接下下来我们更换一下主题，使用yilia，根据个人爱好自己选择其他主题
主题地址：https://github.com/litten/hexo-theme-yilia

下面开始配置yilia主题

1.cd hexoblog/themes/
git clone https://github.com/litten/hexo-theme-yilia.git yilia
cd themes/yilia
git pull


1.修改hexoblog根目录下的 _config.yml ： theme: yilia
2.在博客根目录（注意不是yilia根目录）执行以下命令：
npm i hexo-generator-json-content --save
3.在根目录_config.yml里添加配置：
  jsonContent:
    meta: false
    pages: false
    posts:
      title: true
      date: true
      path: true
      text: true
      raw: false
      content: false
      slug: false
      updated: false
      comments: false
      link: false
      permalink: false
      excerpt: false
      categories: false
      tags: true

4.hexo clean #删除public目录
5.hexo generate #再次生成静态页面

三、常用命令

每次部署的步骤，可按以下2步来进行。

hexo clean

hexo generate

四、其他命令：

hexo new "postName" #新建文章

hexo new page "pageName" #新建页面

hexo generate #生成静态页面至public目录

hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）

hexo deploy #将.deploy目录部署到GitHub

hexo help # 查看帮助

hexo version #查看Hexo的版本
