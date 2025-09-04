## Python 講義：變數與數學運算

### 學習目標
- **理解變數**：能正確宣告、命名、指派與重新指派。
- **熟悉資料型別**：`int`、`float`、`str`、`bool`、`NoneType` 基礎使用。
- **掌握數學運算**：加減乘除、整除、餘數、次方、運算優先順序。
- **會做型別轉換與四捨五入**，避免常見錯誤。

---

### 1. 什麼是變數（Variable）？
變數是用來「儲存資料的名稱」。在 Python 中，首次指派就會自動建立變數，無需事先宣告型別。

```python
# 建立與指派
age = 18
name = "Alice"
height = 1.65  # 公尺
is_student = True

print(age, name, height, is_student)
```

#### 命名規則與建議
- **只能**使用英文字母、數字、底線；不能以數字開頭（例如 `score_1` 可，`1st_score` 不可）。
- **區分大小寫**：`score` 與 `Score` 是不同變數。
- **別用保留字**（如 `for`, `while`, `class`, `True` 等）。
- **可讀性優先**：採用小寫與底線的風格（snake_case），如 `total_price`、`student_count`。

```python
total_price = 199
student_count = 42
# 不建議：tp, sc（語意不明）
```

---

### 2. 常見資料型別（Data Types）
```python
an_int = 10              # int：整數
a_float = 3.14           # float：浮點數
a_str = "hello"         # str：字串
a_bool = False           # bool：布林
a_none = None            # NoneType：空值

print(type(an_int))   # <class 'int'>
print(type(a_float))  # <class 'float'>
print(type(a_str))    # <class 'str'>
print(type(a_bool))   # <class 'bool'>
print(type(a_none))   # <class 'NoneType'>
```

#### 重新指派（Reassignment）
```python
x = 10       # x 為 int
x = 10.5     # 現在 x 為 float
```

#### 多重指派與拆解（Unpacking）
```python
a, b = 1, 2
a, b = b, a  # 交換

x, y, z = [3, 4, 5]  # 從序列拆解
```

---

### 3. 數學運算子（Arithmetic Operators）
- **加**：`+`
- **減**：`-`
- **乘**：`*`
- **除**（浮點）：`/`
- **整除**（商的整數部分）：`//`
- **餘數**：`%`
- **次方**：`**`

```python
print(7 + 3)     # 10
print(7 - 3)     # 4
print(7 * 3)     # 21
print(7 / 3)     # 2.3333333333...
print(7 // 3)    # 2
print(7 % 3)     # 1
print(2 ** 5)    # 32
```

#### 運算優先順序（由高到低）
1. `()` 括號
2. `**`
3. `*`, `/`, `//`, `%`
4. `+`, `-`

```python
print(2 + 3 * 4)       # 14  先乘後加
print((2 + 3) * 4)     # 20  括號優先
print(2 ** 3 ** 2)     # 512  指數為右結合：2 ** (3 ** 2)
```

#### 實務小技巧：
```python
# 複合指定運算子
counter = 0
counter += 1  # 等同 counter = counter + 1
counter *= 2  # 等同 counter = counter * 2
```

---

### 4. 浮點數與精度
電腦中的浮點數採二進位表示，可能出現微小誤差。

```python
print(0.1 + 0.2)           # 0.30000000000000004（非精確 0.3）

# round(數值, 小數位數)
print(round(0.1 + 0.2, 2)) # 0.3
```

如需高精度，可用 `decimal` 模組：
```python
from decimal import Decimal, getcontext

getcontext().prec = 28
print(Decimal('0.1') + Decimal('0.2'))  # 0.3（精確）
```

---

### 5. 型別轉換與輸入
```python
# 數值與字串互轉
age = 18
msg = "年齡為 " + str(age)
print(msg)

price_str = "199"
price = int(price_str)         # 轉 int
pi_str = "3.14159"
pi = float(pi_str)             # 轉 float

# 使用者輸入（input 會回傳字串）
# user_age = int(input("請輸入年齡："))
# print(user_age, type(user_age))
```

---

### 6. 常見錯誤與除錯
- **名稱錯誤（NameError）**：使用了尚未定義的變數。
```python
# NameError: name 'scroe' is not defined（拼字錯）
score = 90
print(scroe)
```

- **型別錯誤（TypeError）**：不相容型別的運算。
```python
# TypeError: can only concatenate str (not "int") to str
age = 18
print("Age: " + age)

# 正確作法
print("Age: " + str(age))
```

---

### 7. 綜合範例
```python
name = "Amy"
eng = 85
math = 92

total = eng + math
avg = total / 2

print(f"{name} 的總分: {total}")
print(f"{name} 的平均: {round(avg, 1)}")
```

---

### 8. 練習題（建議自主完成）
1. 建立變數 `length = 20`、`width = 12.5`，計算長方形面積與周長。
2. 使用三個變數 `a = 7`、`b = 3`、`c = 2`，計算 `(a + b) ** c` 與 `a + b ** c` 的差異，並解釋原因。
3. 請撰寫程式：輸入 `n`（整數），輸出 `n` 的平方與立方。
4. 將輸入的攝氏溫度（浮點數）轉換為華氏溫度，公式：`F = C * 9 / 5 + 32`，結果四捨五入到小數第 1 位。
5. 假設帳單金額為 `subtotal`，服務費為 10%，稅率為 5%，計算最終金額（四捨五入到整數）。

---

### 9. 參考與建議
- **善用 `type()` 與 `print()`** 觀察變數當下的型別與值。
- **命名具語意**，讓讀 code 的人（包含未來的你）更快上手。
- **必要時使用 `round()` 或 `decimal`**，處理浮點數精度問題。


