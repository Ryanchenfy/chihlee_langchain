# Python 基礎：變數與數學運算

## 目錄
1. [什麼是變數](#什麼是變數)
2. [變數的命名規則](#變數的命名規則)
3. [變數的資料型別](#變數的資料型別)
4. [數學運算符號](#數學運算符號)
5. [運算優先順序](#運算優先順序)
6. [實際範例](#實際範例)
7. [練習題](#練習題)

---

## 什麼是變數

變數就像是一個**容器**，用來儲存資料。在Python中，我們可以將資料指派給變數，之後就可以使用這個變數來存取資料。

### 基本概念
- 變數是一個**標籤**，指向記憶體中的資料
- 可以隨時改變變數的值
- 變數名稱對應到實際的資料內容

---

## 變數的命名規則

### ✅ 正確的命名方式
```python
# 使用英文字母
name = "小明"
age = 18

# 使用底線分隔單字
student_name = "小華"
first_name = "王"

# 使用數字（但不能開頭）
score1 = 95
test2 = 88

# 大小寫敏感
Name = "小李"    # 與 name 是不同的變數
NAME = "老李"    # 與 Name 也是不同的變數
```

### ❌ 錯誤的命名方式
```python
# 不能以數字開頭
1name = "小明"      # 錯誤！

# 不能使用特殊符號（除了底線）
my-name = "小華"    # 錯誤！
my@name = "小李"    # 錯誤！

# 不能使用Python關鍵字
if = "條件"         # 錯誤！
for = "迴圈"        # 錯誤！
```

### Python關鍵字列表
```python
# 以下都是Python的保留字，不能當作變數名稱
False, None, True, and, as, assert, break, class, continue, def, del, elif, else, except, finally, for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield
```

---

## 變數的資料型別

### 1. 整數 (int)
```python
age = 18
score = 100
temperature = -5
```

### 2. 浮點數 (float)
```python
height = 175.5
weight = 65.8
pi = 3.14159
```

### 3. 字串 (str)
```python
name = "小明"
message = '你好，世界！'
address = """台北市
信義區
101大樓"""
```

### 4. 布林值 (bool)
```python
is_student = True
is_working = False
```

### 5. 檢查資料型別
```python
x = 42
y = 3.14
z = "Hello"

print(type(x))    # 輸出：<class 'int'>
print(type(y))    # 輸出：<class 'float'>
print(type(z))    # 輸出：<class 'str'>
```

---

## 數學運算符號

### 基本運算符號

| 運算符號 | 名稱 | 範例 | 結果 |
|---------|------|------|------|
| `+` | 加法 | `5 + 3` | `8` |
| `-` | 減法 | `10 - 4` | `6` |
| `*` | 乘法 | `6 * 7` | `42` |
| `/` | 除法 | `15 / 3` | `5.0` |
| `//` | 整數除法 | `17 // 3` | `5` |
| `%` | 取餘數 | `17 % 3` | `2` |
| `**` | 次方 | `2 ** 3` | `8` |

### 範例程式碼
```python
# 基本運算
a = 10
b = 3

print(f"a = {a}, b = {b}")
print(f"加法：{a} + {b} = {a + b}")
print(f"減法：{a} - {b} = {a - b}")
print(f"乘法：{a} * {b} = {a * b}")
print(f"除法：{a} / {b} = {a / b}")
print(f"整數除法：{a} // {b} = {a // b}")
print(f"取餘數：{a} % {b} = {a % b}")
print(f"次方：{a} ** {b} = {a ** b}")
```

### 複合指派運算符號

| 運算符號 | 範例 | 等同於 |
|---------|------|--------|
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 3` | `x = x - 3` |
| `*=` | `x *= 2` | `x = x * 2` |
| `/=` | `x /= 4` | `x = x / 4` |
| `//=` | `x //= 2` | `x = x // 2` |
| `%=` | `x %= 3` | `x = x % 3` |
| `**=` | `x **= 2` | `x = x ** 2` |

### 範例程式碼
```python
x = 10
print(f"初始值：x = {x}")

x += 5    # x = x + 5
print(f"x += 5 後：x = {x}")

x -= 3    # x = x - 3
print(f"x -= 3 後：x = {x}")

x *= 2    # x = x * 2
print(f"x *= 2 後：x = {x}")

x /= 4    # x = x / 4
print(f"x /= 4 後：x = {x}")
```

---

## 運算優先順序

### 運算優先順序（由高到低）
1. **括號** `()` - 最高優先順序
2. **次方** `**`
3. **正負號** `+x`, `-x`
4. **乘法、除法、取餘數** `*`, `/`, `//`, `%`
5. **加法、減法** `+`, `-`

### 範例說明
```python
# 範例1：基本運算
result1 = 2 + 3 * 4
print(f"2 + 3 * 4 = {result1}")    # 輸出：14 (先算 3*4=12，再加2)

# 範例2：使用括號改變優先順序
result2 = (2 + 3) * 4
print(f"(2 + 3) * 4 = {result2}")  # 輸出：20 (先算 2+3=5，再乘4)

# 範例3：複雜運算
result3 = 2 ** 3 + 4 * 2 - 1
print(f"2 ** 3 + 4 * 2 - 1 = {result3}")  # 輸出：15
# 計算順序：2**3=8, 4*2=8, 8+8-1=15
```

---

## 實際範例

### 範例1：計算圓的面積
```python
# 計算圓的面積：A = πr²
import math

radius = 5
pi = math.pi
area = pi * radius ** 2

print(f"圓的半徑：{radius}")
print(f"圓周率：{pi:.4f}")
print(f"圓的面積：{area:.2f}")
```

### 範例2：溫度轉換
```python
# 攝氏轉華氏：F = C × 9/5 + 32
celsius = 25
fahrenheit = celsius * 9/5 + 32

print(f"攝氏溫度：{celsius}°C")
print(f"華氏溫度：{fahrenheit}°F")
```

### 範例3：計算成績平均
```python
# 計算三科成績的平均分數
math_score = 85
english_score = 92
science_score = 78

total_score = math_score + english_score + science_score
average_score = total_score / 3

print(f"數學：{math_score}分")
print(f"英文：{english_score}分")
print(f"自然：{science_score}分")
print(f"總分：{total_score}分")
print(f"平均：{average_score:.1f}分")
```

---

## 練習題

### 練習1：基本運算
```python
# 請計算以下運算的結果
a = 15
b = 4

# 請寫出以下運算的結果
print("練習1：基本運算")
print(f"a = {a}, b = {b}")
print(f"a + b = ?")      # 請計算
print(f"a - b = ?")      # 請計算
print(f"a * b = ?")      # 請計算
print(f"a / b = ?")      # 請計算
print(f"a // b = ?")     # 請計算
print(f"a % b = ?")      # 請計算
print(f"a ** b = ?")     # 請計算
```

### 練習2：複合運算
```python
# 請計算以下運算的結果
x = 20
y = 6

print("練習2：複合運算")
print(f"初始值：x = {x}, y = {y}")

# 請計算以下運算後的x值
x += y        # x = ?
x *= 2        # x = ?
x -= 5        # x = ?
x //= 3       # x = ?

print(f"最終x值：{x}")
```

### 練習3：實際應用
```python
# 小明去超市買東西，請計算總金額
apple_price = 25      # 蘋果單價
apple_count = 6       # 蘋果數量
banana_price = 15     # 香蕉單價
banana_count = 8      # 香蕉數量
discount = 0.9        # 9折優惠

# 請計算：
# 1. 蘋果總價
# 2. 香蕉總價
# 3. 折扣前總價
# 4. 折扣後總價

print("練習3：購物計算")
# 請完成計算...
```

---

## 總結

### 重點回顧
1. **變數**是儲存資料的容器，可以隨時改變值
2. **命名規則**：不能以數字開頭，不能使用特殊符號和關鍵字
3. **資料型別**：整數、浮點數、字串、布林值等
4. **數學運算**：加減乘除、次方、取餘數等
5. **運算優先順序**：括號 > 次方 > 乘除 > 加減

### 下一步學習
- 字串操作
- 條件判斷
- 迴圈結構
- 函數定義

---

## 參考資源
- [Python官方文件](https://docs.python.org/)
- [Python教學網站](https://www.python.org/about/gettingstarted/)
- [Python變數命名慣例](https://www.python.org/dev/peps/pep-0008/)

---

*最後更新：2024年*
