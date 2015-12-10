

##1. 請解釋 database.yml, routes.rb, 和 Gemifle 分別是什麼？ 他們分別在一個 Rails 專案裡的什麼位置？ 他們為什麼對一個 Rails 專案如此重要？
```ruby
Ans: 
database.yml: 設定DB資訊的地方
route.rb: rails專案有那些路由(設定網頁路徑的地方)
gemfile: 記錄使用那些library與版本資訊
```



##2. MVC 架構裡的 M, V, 和 C 分別代表什麼？
```ruby
Ans: 
M: Model: 和DB的資料表對應
V: View: 前台顯示內容
C: Controller:負責處理前端的action
```

##3. 請解釋 CRUD 是哪四個字的縮寫？
```ruby
Ans: 
Create
Read
Update
Delete
```

##4. 請問在 routes.rb 裡面加入以下程式碼會產生出哪一些 url？ (提示：在 browser 輸入http://localhost:3000/rails/info/routes)

resources :users

```ruby
Ans:
localhost:3000/
localhost:3000/users
```




##5. 請解釋 model 檔案和 migration 檔案的差別
```ruby
Ans: 
model是對應資料庫中的某個資料表
migration相反(更改資料庫欄位現有的狀態)
```



##6. 若今天發現一個 migration 檔寫錯，請問我應該用什麼指令回復到上一個版本的 migration?
```ruby
Ans:
rake db:rollback
```


##7. 假設今天
我要在資料庫裡產出一個叫 group 的資料表
裡面包括的欄位名稱和相對應的資料型別是： name (string), description (text), members (integer)
請寫出一個能產生出以上需求的 migration 檔
```ruby
Ans: 
class AddGroupTable <ActiveRecord::Migration
	def change
		create_table :groups do |t|
		t.string:name
		t.text:description
		t.integer:member
	t.timestamps
	end
end
end

```





##8. 請解釋什麼是 ActiveRecord?
```ruby
Ans: 
1. Rails核心元件之一，可用ruby語法就可操作DB, ActiveRecord會翻譯成SQL語法再去DB執行
2. ActiveRecord是rails的ORM
```







