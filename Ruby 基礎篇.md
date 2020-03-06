# Ruby 基礎篇

## 有趣的程式語言

### 發明的目的：希望工程師寫得開心

### 有很多黑魔法，讓學習者快速取得成就感

- 代價：你不知道他怎麼做到的，缺點是想改改不動

### 都市傳說

- 聽說Ruby很慢

	- 是不快，但沒有慢到跑不動。慢是要看跟誰比，Ruby為了讓你好寫，加了許多功能，所以會犧牲一些效能。

		- Twitter 的慢跟你的慢，概念上不一樣。他是幾億人在用，你可能幾個人而已。等你做到那個量再來煩惱，那是有錢人的煩惱。

- 寫Ruby要先買Mac

	- 單純只是因為Mac環境比較友善，並非Windows不能用來開發。

## 目標

### 看懂Rails專案程式碼

- 夠用即可

## 什麼是Ruby?

### 泛用型

- 不是只用來開發網站

### 腳本式

- 程式語言分類

	- 編譯 compile

		- 必須編譯後才能執行
		- 通常效能較好

	- 腳本式

		- 可以直接呼叫、執行
		- 開發流程較短
		- 效能稍微差一點，沒有經過編譯最佳化

### 物件導向程式語言

- 在Ruby的世界，所有東西幾乎都是物件

### Rails 不是程式語言，是一種框架(或說套件)

### 有許多衍生實作品

- 正宗版 CRuby 又稱 MRI

	- 用C語言開發出來的

- JRuby 又稱JVM
- mRuby

	- 主要用於嵌入式系統

## Gem

### 套件安裝工具

- Ruby套件登記網站
https://rubygems.org/?locale=zh-TW

### 前端圈用的是npm(是一家商業公司運營)

- 故事 npm left pad chaos

## 程式沒有強弱之分，只有適不適合。

### 主要差別在於生態圈，大家都用它來幹嘛，相關資源就比較多，開發起來也比較輕鬆

- 例如 Python 是因為有很多人幫你做好ai ml 套件，所以大家都用Python來做ai

## 常見的開發與使用

### irb 用來做簡單的練習

### 在終端機中執行.rb 檔案

- 先到對應的目錄，開一個xxx.rb，把指令寫進去後存檔，在終端機輸入 $ ruby xxx.rb，就可以執行
- 副檔名改成.php / .jpg 也還是可以動

	- 副檔名只是為了方便識別，讓你的檔案跟電腦中的城市建立關聯，方便快速開啟，實際上終端機是看內容的code 及 執行主程式是什麼。

## 註解 Comment

### 單行註解

- #這裡打註解內容 （內容不會被執行）

	- 用於說明這段程式碼在幹嘛
	- 暫時關閉某行程式碼
	- 快速鍵 com + / (選定單行多行都可以)

### 多行註解

- =begin ..... =end

## Coding Style

### 口音(只是習慣，不成文規定)

- Ruby口音字典： https://github.com/rubocop-hq/ruby-style-guide

	- 口音不同，寫起來一樣會動，只是看起來像外地人

- e.g

	- Ruby 的縮排，用的是2個空格（不是Tab 或4個空格）

### 命名慣例

- 駝峰

	- camlCase

		- firstName

			- C Java

- 蛇式

	- snake_case

		- first_name

			- PHP Ruby Python

## 變數variable與常數Constant

### 為什麼要用變數？

- 方便呼叫/存取物件(某個資料/記憶體)

	- 如：同學桌上的名牌，方便呼叫

		- 子主題 1

	- 只是一個標籤，沒有型態，不是具體的東西，用來代表變數中"實際的東西"

- 變數分類：區域 全域 實體 類別

	- 區域- xxx = ""

		- 在一個區域內存取

	- 全域- $xxx = ""

		- 雖可以到處存取，但盡量不要用

- 範例

	- name = "ABC"
age = 18
puts name
puts age

- 可一次指定多個變數

	- x, y, z = [1, 2, 3]

- a = a + 2

	- 這不是一個數學公式

		- = 是指定的意思

			- ：把右邊的結果指定給左邊

	- 簡化

		- a = +2

			- a += 2

				- 不好懂就不要這樣寫

					- 必須重視程式碼可讀性，不能自己下次打開看不懂，也沒有效能問題，盡量遵照一套風格即可

	- 會先計算右邊的結果

- 當你沒有定義變數時，呼叫並執行，會無法執行，因為沒東西
- 給變數取一個"好名字"，才不用寫一大堆註解，方便未來維護

	- (X)

		- a =1, x = 3

	- (O)

		- age = 1, height = 10

- 交換變數

	- x = 2
y = 3

#方法一:比較標準的解法，大部分語言中會用到
t = x #把x指定給t
x = y #把y指定給x
y = t #把t指定給y

#方法二:Ruby 多重指定法（作弊）不是每個程式都會有
#x, y = y ,x

#方法三
#how to switch two variables without the third one
x = x + y
y = x - y
x = x - y

puts x
puts y

### 常數Constant：希望它在運轉的過程不會被改變，也不應該去修改

- 命名：大寫開頭

	- Name = "aaa"

		- Name = "aaa"
Name = "bbb"

- 使用情境：資料庫密碼、金鑰
- 理論上不能修改，但Ruby中會出現警告，還是可以修改（實務上不要改！！

	- 警告，這樣做不好，但我免強允許你

		- 我警告你手不要放過來

	- 錯誤，就是不能動

		- 直接給你一巴掌

### 關鍵字或保留字，不要用來當變數或常數，盡量避開

- if / else / true / false / nil ...

### 有什麼不一樣？

- 在Ruby中，因為兩者都可以改，所以僅剩命名上的差別

## 字串 String

### 用雙引號、單引號括起來的文字

- "xxx", 'xxx'

	- 若要帶變數，就用雙引號
	- 確定不會有變數，就用單引號

- 沒有不同，但串接時，效果不同

	- 字串串接方法

		- #{變數名}

			- 用單引號時，不會帶入值

### 跳脫字元 escape：\

- 引號會早最近的引號配對

	- 'Hi I'm Joseph'

		- 改成

			- 'Hi I\'m Joseph'

	- "He said "Hi""

		- 改成

			- "He said \"Hi\""

- 取代引號的方法，就不需要跳脫字元的狀況，方便許多

	- %Q("xxx")

		- 等同雙引號

	- %q('xxx')

		- 等同單引號

## 邏輯判斷與流程控制

### if

- 如果...就做...不是...就做...

	- weather = "下雨"
if weather == "下雨"
  puts "宅在家"
end

		- == 做比較
		- if weather == 會去判斷真或假

			- Boolean 布林型態：只有真或假兩種型態

				- Ruby中有兩個是假的：false, nil(代表不存在)。
0, -1 [] {} 在Ruby中都是真的，很程式語言中是假的

					- nil：是存在的物件，但代表不存在
					- true false nil 在Ruby中是已經被定義好的物件，不能被修改

- 倒裝句

	- 只有一行判斷時

		- weather = "下雨"
if weather == "下雨"
  puts "宅在家"
end

			- puts "宅在家" if weather == "下雨"

### unless

- weather = "出太陽"
if not weather == "下雨"
  puts "出去玩"
end

	- unless weather = "下雨"
  puts "出去玩"
end

		- 不要為了unless 而 unless

			- 他沒有說不想宣布要不要不選里長

### if else

- weather = "下雨"
if weather == "下雨"
  puts "宅在家"
else
  puts "出去玩"
end

### 三元運算子

- gender = 1
title = (gender == 1) ? "先生" : "小姐"
puts title   # => 先生

	- 不一定要這樣寫，你自己看得懂最重要

### if elsif else

- weather = "下雨"
if weather == "下雨"
  puts "宅在家"
elsif weather == "出太陽"
  puts "出去玩"
else
  puts "睡覺"
end

### case when

- weather = "下雨"

case weather
when "下雨"
  puts "待在家!"
when "出太陽"
  puts "出去玩!"
else
  puts "在家睡覺!"
end

	- 選項多，3個以上時，大部分人會這樣寫
	- 超能力

		- age = 10

if age >= 0 && age <= 3
  puts "Baby"
elsif age >= 4 && age <= 10
  puts "Kids"
elsif age >= 11 && age <= 17
  puts "Teenager"
else
  puts "Adult"
end

			- 可改成

				- age = 10

case age
when 0..3
  puts "Baby"
when 4..10
  puts "Kids"
when 11..17
  puts "Teenager"
else
  puts "Adult"
end

					- 0..3 範圍

- 實際運作還是if else，他只是個語法糖衣，寫起來比較開心

## 在畫面印出東西的方法

### print

- 印出，不換行，無回傳值

### puts

- 印出，換行，無回傳值

### p

- 印出，換行，有回傳值，有"  "

## Ruby中的等號，很多時候不是等號

### 很多時候加號不是加號，減號不是減號

- 1 + 2

	- 原型：1 .+ (2) 實際上是1物件，呼叫一個+方法，帶入2的值

## 例外處理(防呆機制)

### def bmi_calculator(height, weight)
  begin
    weight / (height * height)
  rescue
    "輸入的數字有問題"
  end
end

## 方法 Method (函數、函式)

### 就是一批程式碼的組合

- 定義 
def xxx (a, b)
  .....
end
- 使用時 xxx()

### 為什麼要用？

- 賦予一個有意義的名字，方便整理與使用，從名字就可以知道這些程式碼在幹嘛
- 給一個名字，想要使用時只要呼叫方法的名字，就會去執行方法中的程式碼，便於重複使用、容易使用

### 參數 Parameter

- 定義時給的值

	- def xxx (參數)

### 引數 Argument

- 使用時帶入的

	- xxx (123)

### 適當的省去小括號

- say_hi('孫悟空') = say_hi '孫悟空'

	- age = 18

def age
  20
end

puts age  # => 會得到 18 還是 20？

		- 答案是 18，因為 Ruby 在同一個範圍內，如果遇到同名的區域變數及方法，會以區域變數優先

### 在Ruby中，最後一行的運算結果，若沒有強調，就是回傳值(沒寫return也是，所以最後一行的return可以省略)

### 不管true或false都會做的事，就抽出來放外面

## 數字

### 整數/整數

- 會得出整數，會自動捨去小數點後的數字

	- 只要其中一個數字有小數點，計算才會有小數點

## 回傳值

### 回傳 = 交回控制權

- 程式是一行一行往下跑

### 例外

- def age
  return 20
  10
end

puts age

	- return是交回控制權，所以跑到第2行就交回控制權了，那第三行就不會跑。

*XMind: ZEN - Trial Version*