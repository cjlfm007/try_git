Models in Rails use a singular name, and their corresponding database tables use a plural name. 

A controller's purpose is to receive specific requests for the application. Routing decides which controller receives which requests. Often, there is more than one route to each controller, and different routes can be served by different actions. Each action's purpose is to collect information to provide it to a view.

A view's purpose is to display this information in a human readable format. An important distinction to make is that it is the controller, not the view, where information is collected. The view should just display that information. By default, view templates are written in a language called eRuby (Embedded Ruby) which is processed by the request cycle in Rails before being sent to the user.

Migrations are Ruby classes that are designed to make it simple to create and modify database tables. Rails uses rake commands to run migrations, and it's possible to undo a migration after it's been applied to your database. Migration filenames include a timestamp to ensure that they're processed in the order that they were created.



Resources:
2.2 CRUD、HTTP 動詞以及動作
在 Rails 裡，資源式路由提供 HTTP 動詞、URL、Controller 動作，這三者的對應關係。按照慣例，每個動作會對應到資料庫特定的 CRUD 操作。假設路由檔案裡有一條路由宣告為：

resources :photos
會建立出七筆不同的路由，皆對應到 PhotosController：

HTTP 動詞	路徑	Controller#動作	用途

GET	/photos	photos#index	顯示所有圖片

GET	/photos/new	photos#new	回傳建立新圖片的表單

POST	/photos	photos#create	建立新圖片

GET	/photos/:id	photos#show	顯示特定圖片

GET	/photos/:id/edit	photos#edit	回傳編輯圖片的表單

PATCH/PUT	/photos/:id	photos#update	更新特定圖片

DELETE	/photos/:id	photos#destroy	刪除特定圖片

