'''ruby

1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異
Ans: 
Fixnum: 直接呈現整數
Float: 計算結果可以有小數點, 浮點數不能被1整除

2. 今天有兩個字串：
str1 = "Hallo Welt!" 
str2 = " NTU Rails 261!"
請說明以下兩個印出字串的方式的不同處：
Ans: 
puts str1 + str2
直接把str1和str2顯示
puts "#{str1}#{str2}"
#表示是變數，{}內的值會經過運算後呈現結果,
字串內插的方式，避免記憶體的浪費

3. 請解釋 array 和 hash 的不同處
Ans: 
array是有排序過值(有index在內)，hash是將兩個值配成一對


4. 請寫一段 code 從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值
Ans: 
arr = [1, "a string", 3.14, [1,2,3,4]]
arr.select {|x| x.class !=string}






5. 請列出兩種產出亂數的方法
Ans: 
rand(1..3)
(1..3).shuffle!



6. 請把 lesson1 程式碼裡的 calculator.rb 裡面的使用者輸入兩個數字的方式改寫成 method，並要有防止使用者亂輸入值的功能
Ans:
def firstnumber()
  begin
    puts "Please enter the first number:"
    num = gets.chomp.to_i
    end while ![Fixnum, Float].include?(num)
    num
  end
  def secondnumber()
    put "Please enter the second number:"
    num = gets.chomp.to_i
    end while ![Fixnum,Float].include?(num)
    num
  end





7. 以下這段程式碼：
((1 > 3)&&(true == true))||(!!!false)
會執行出什麼結果？ 請試試不用 irb 算出結果
Ans: true

8. 請問 binding.pry 是什麼？ 要如何使用它？
Ans: 
可以在程式碼執行時攔截呼叫
在程式中加上binding.pry，即可做為中斷點，以檢查和debug

9. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行
var = 5
if var >= 5
  return "var is greater than or equal to 5"
else
  return "var is less than 5"
end

Ans: 
var = 5
var >= 5 ? "var is greater than or equal to 5" : "var is less than 5"

'''