##1. 請用簡單的方式敘述以下每一行程式碼：
```ruby
Ans:
a = 1 				#a的值為1
@a = 2				#a的instance variable為2
@@a = 5				#a的class variable為5
user = User.new		#在user這個class下，新增一個"User"物件
user.name			#呼叫user這個class的name
user.name = "Joe"	#指定user這個class的name是Joe
```

##2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?
```ruby
Ans:
模組的 Module 類別正是類別的 Class 類別的父類別，與class相似，除了
1. 模組並沒有實例。
2. 模組並沒有子類別。
3. 模組由 module ... end 定義。
```



##3. 請說明 class 和 instance variable 之間的差別
```ruby
Ans:
class:類別，用以定義物件的分類。
instance variable: 屬於該類別的物件為instance。instance variable用以描述instance的特徵，可在同一個class的各種method之間互相傳遞
```

##4. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是:

User.new("Bob", "male", "Engineer")
請寫出 User class 的 initialize method

```ruby
Ans:
  class User
    def initialize(name, gender, job)
      @name = "name"
      @gender = "gender"
      @job = "job"
    end
  end
```

##5. self 在： a. class 裡，method 外面 b. class 裡，instance method 裡 分別是指向什麼?
```ruby
Ans: 
a. 指向class自己
b. 指向class下的某個instance自己
```

##6. attr_accessor 的功能是什麼
```ruby
Ans:
attr_accessor 會在 Ruby 的類別裡產生一對 getter 以及 setter 方法
```

##7. 請說明 public 和 private method 之間的不同
```ruby
Ans:
public method, 在物件外部即可呼叫，預設值
private method，在物件內部才能呼叫
```

##8. Ruby 是如何確保一個 module 的 method 會被 include 它的 class 使用到？ (提示：method lookup)
```ruby
Ans:
利用.ancestors找祖先
```
