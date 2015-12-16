##1. �л��� rails g scaffold xxx �\�઺�a�B����H
```ruby
Ans: 
���@�w�ŦX�ݨD�A�B�|���ͤ����n���ɮשθ�Ƨ�
```

##2. �Y���ѻݭn�� Project �M Issue �o��� Model �إߤ@��h�����Y�A�мg�X��@�W�һݭn�� migratiion �M model �ɮ�
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

##3. �Y���ѧڦ��H�U model �ɡG

class User < ActiveRecord::Base
  has_many :groups_users
  has_many :groups, through: :groups_users 
end
�мg�X�M�o�� model �ɬ����s�� model �ɡA�H�γo�� model �ɩһݭn����Ʈw���
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

##4. �����3�D�A�p�G�ݭn���@�ӥs "Bob" ���ϥΪ̲��ͤ@�ӦW�r�s�� "Rails is Fun" �����ΡA���Ӧp��b rails console �̹�@�X�ӡH
```ruby
Ans: 
1. 
bob = User.create(name: "Bob")
group = Group.create(title: "Rails is Fun")
bob.groups << group 


```

##5. �����4�D�A�мg�@�q�{���X�T�O�ϥΪ̦b�إ߷s���ήɪ��ΦW�r���i�H�O�ťաA�ӥB����W�L50�Ӧr
```ruby
Ans: 
1. 
class Group < ActiveRecord::Base
	has_many :groups
	has_many :users, through: :groups_users

	validate :title, presence: true, length: {maximum :50}
end
```

##6. �ЦC�X��ؤ�k�ˬd�b routes.rb �̭��]�w������
```ruby
Ans: 
1. 
�}��terminal, ��Jrake routes
�}��Server�s�����A���}�C��Jlocalhost:3000/rails/info/routes
```

##7. �ЦC�X�b�@�� rails �M�׸̨ϥ� bootstrap �M�󪺨B�J
```ruby
Ans: 
1. ��rails�M�ת�gemfile�̭��[�Jgem 'bootstrap-sass'
2. terminal->�brails�M�׸��|�U->��Jbundle install
3. �bapp/assets/stylesheets/application.css�̿�J@import 'bootstrap'
4. �bapp/assets/javascript/application.js�̿�J //=require bootstrap
```

##8. �л����b .erb �ɮ׸� <%= %> �P <% %> �o��� tag ���t�O
```ruby
Ans: 
1. 
<%= %>�A�i��<%=��%>���O�Jruby�{���X�A�|��Xruby�{�����浲�G
<% %>�A���|��X���󵲪G�A�`�Φbif�ΰj����󤤡C
```






