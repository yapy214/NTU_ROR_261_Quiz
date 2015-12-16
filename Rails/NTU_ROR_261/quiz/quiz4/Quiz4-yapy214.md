##1. 請說明 rails g scaffold xxx 功能的壞處為何？
```ruby
Ans: 
不一定符合需求，且會產生不必要的檔案或資料夾
```

##2. 若今天需要為 Project 和 Issue 這兩個 Model 建立一對多的關係，請寫出實作上所需要的 migratiion 和 model 檔案
```ruby
Ans: 
class Project < ActiveRecord::Base
	has_many :issues
end

class Issue < ActiveRecord::Base
	belongs_to :project
end



class ProjectIssueTable < ActiveRecord::Migration
	def change
		create_table :projects do |t|
			t.string :project_name
			t.timestamps null:false
		end

		create_table :issues do |t|
			t.string :issue_ID
			t.integer :project_id
			t.timestamp null:false
		end
	end
end
```

##3. 若今天我有以下 model 檔：

class User < ActiveRecord::Base
  has_many :groups_users
  has_many :groups, through: :groups_users 
end
請寫出和這個 model 檔相關連的 model 檔，以及這些 model 檔所需要的資料庫欄位
```ruby
Ans: 
1. 
class Group < ActiveRecord::Base
	has_many :groups
	has_many :users, through: :groups_users
end

class GroupsUser < ActiveRecord::Base
	belongs_to :group
	belongs_to :user
end
```

##4. 延續第3題，如果需要讓一個叫 "Bob" 的使用者產生一個名字叫做 "Rails is Fun" 的社團，應該如何在 rails console 裡實作出來？
```ruby
Ans: 
1. 
bob = User.create(name: "Bob")
group = Group.create(title: "Rails is Fun")
bob.groups << group 


```

##5. 延續第4題，請寫一段程式碼確保使用者在建立新社團時社團名字不可以是空白，而且不能超過50個字
```ruby
Ans: 
1. 
class Group < ActiveRecord::Base
	has_many :groups
	has_many :users, through: :groups_users

	validate :title, presence: true, length: {maximum :50}
end
```

##6. 請列出兩種方法檢查在 routes.rb 裡面設定的路由
```ruby
Ans: 
1. 
開啟terminal, 輸入rake routes
開啟Server瀏覽器，網址列輸入localhost:3000/rails/info/routes
```

##7. 請列出在一個 rails 專案裡使用 bootstrap 套件的步驟
```ruby
Ans: 
1. 到rails專案的gemfile裡面加入gem 'bootstrap-sass'
2. terminal->在rails專案路徑下->輸入bundle install
3. 在app/assets/stylesheets/application.css裡輸入@import 'bootstrap'
4. 在app/assets/javascript/application.js裡輸入 //=require bootstrap
```

##8. 請說明在 .erb 檔案裡 <%= %> 與 <% %> 這兩種 tag 的差別
```ruby
Ans: 
1. 
<%= %>，可於<%=到%>中嵌入ruby程式碼，會輸出ruby程式執行結果
<% %>，不會輸出任何結果，常用在if或迴圈條件中。
```






