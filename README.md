随便玩玩
===

# 创建controller
rails generate controller Articles

# 创建model
rails generate model Article title:string text:text (会自动生成迁移文件)

rails generate model Comment commenter:string body:text article:references

# 用户注册登录
rails g model user name:string email:string password_digest:string

rails g controller users signup

rails g migration AddAuthTokenToUsers auth_token:string

# 分页
https://github.com/amatsuda/kaminari

rails g kaminari:config

# 文件上传
https://github.com/carrierwaveuploader/carrierwave

rails generate uploader Avatar

# 多态
rails g migration CreatePictures name:string imageable_id:integer imageable_type:string

# 邮件
rails g mailer UserMailer

# 微信登录
http://www.ngrok.cc/

# 导入Bootstrap
Actually you don't need gem for this, here is the step to install Bootstrap 3 in RoR

Download Bootstrap

Copy:

bootstrap/dist/css/bootstrap.css and bootstrap/dist/css/bootstrap.min.css

To: vendor/assets/stylesheets

Copy:

bootstrap/dist/js/bootstrap.js and bootstrap/dist/js/bootstrap.min.js

To: vendor/assets/javascripts

Update: app/assets/stylesheets/application.css by adding:

*= require bootstrap.min
Update: app/assets/javascripts/application.jsby adding:

//= require bootstrap.min
With this you can update bootstrap any time you want, don't need to wait gem to be updated. Also with this approach assets pipeline will use minified versions in production.
