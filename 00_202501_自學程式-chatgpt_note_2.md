## Question : 要準備資訊能力測驗 , 可以以基本能力範圍: 輸入與輸出 (input and output), 算術運算 (arithmetic operation)，邏輯運算 (logical operation)，位元運算 (bitwise operation), 條件判斷與迴路 (conditional expressions and loop), 陣列與結構 (arrays and structures), 字元 (character)，字串 (string), 函數呼叫與遞迴 (function call and recursion), 每個單元 5 到 10 範例, 來準備測驗

## 我可以為你準備每個單元的範例題目，並提供解釋與程式碼範例。你希望我使用哪種程式語言來示範？例如 C、Python、Java 或其他？==> C、Python、Java

## 太好了！我會以 C 語言為每個單元提供 5 到 10 個範例，並附上詳細解釋與程式碼。我們可以按照主題逐步進行，或者一次提供所有範例，你比較喜歡哪種方式？ ==> 逐步




我們從 **輸入與輸出 (Input and Output)** 開始。這是 C 語言的基礎，掌握好輸入與輸出對後續學習很重要。  

## **輸入與輸出 (Input and Output)**
C 語言主要使用 `printf()` 來輸出，`scanf()` 來輸入。此外，`gets()` 和 `puts()` 也可以用來處理字串輸入輸出。

### **範例 1：輸出文字**
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
**解釋**：
- `printf()` 用於輸出文字，`\n` 代表換行。

---

### **範例 2：輸入與輸出整數**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個整數: ");
    scanf("%d", &num);
    printf("你輸入的數字是: %d\n", num);
    return 0;
}
```
**解釋**：
- `scanf("%d", &num);` 讀取使用者輸入的整數。
- `&num` 代表變數的記憶體位置，確保 `scanf()` 正確存入數值。

---

### **範例 3：輸入與輸出浮點數**
```c
#include <stdio.h>

int main() {
    float num;
    printf("請輸入一個浮點數: ");
    scanf("%f", &num);
    printf("你輸入的數字是: %.2f\n", num);
    return 0;
}
```
**解釋**：
- `%f` 用於輸入浮點數，`%.2f` 表示輸出時顯示 2 位小數。

---

### **範例 4：輸入與輸出字元**
```c
#include <stdio.h>

int main() {
    char ch;
    printf("請輸入一個字元: ");
    scanf(" %c", &ch);  // 注意前面的空格
    printf("你輸入的字元是: %c\n", ch);
    return 0;
}
```
**解釋**：
- `%c` 用於讀取單一字元。
- `scanf(" %c", &ch);` 前面加空格是為了忽略前一次輸入的換行符號。

---

### **範例 5：輸入與輸出字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個字串: ");
    scanf("%s", str);
    printf("你輸入的字串是: %s\n", str);
    return 0;
}
```
**解釋**：
- `%s` 用於讀取字串，但 `scanf("%s", str);` 只能讀取單一單詞，遇到空格會停止。

---

### **範例 6：使用 `gets()` 和 `puts()` 處理字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個句子: ");
    gets(str);
    printf("你輸入的句子是: ");
    puts(str);
    return 0;
}
```
**解釋**：
- `gets(str);` 允許讀取整行字串（包含空格）。
- `puts(str);` 直接輸出字串並換行。

⚠ **注意**：`gets()` 可能會造成緩衝區溢位 (Buffer Overflow)，建議改用 `fgets()`。

---

### **範例 7：使用 `fgets()` 來安全讀取字串**
```c
#include <stdio.h>

int main() {
    char str[100];
    printf("請輸入一個句子: ");
    fgets(str, sizeof(str), stdin);
    printf("你輸入的句子是: %s", str);
    return 0;
}
```
**解釋**：
- `fgets(str, sizeof(str), stdin);` 讀取包含空格的字串，確保不超過陣列大小，避免溢位問題。

---

你可以先試試這些範例，看看有沒有問題或需要補充的部分！如果沒問題，我們可以進入下一個單元 **算術運算 (Arithmetic Operation)** 🚀

好的！我們現在來學習 **算術運算 (Arithmetic Operation)**，這是 C 語言的基本數學運算，在計算與資料處理中非常重要。  

---

## **算術運算 (Arithmetic Operation)**
C 語言提供了基本的數學運算符號：

| 運算符號 | 說明 |
|---------|------|
| `+` | 加法 (Addition) |
| `-` | 減法 (Subtraction) |
| `*` | 乘法 (Multiplication) |
| `/` | 除法 (Division) |
| `%` | 取餘數 (Modulo, 只適用於整數) |

這些運算符可以搭配變數與數值來進行數學運算。

---

### **範例 1：基本四則運算**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    printf("加法: %d + %d = %d\n", a, b, a + b);
    printf("減法: %d - %d = %d\n", a, b, a - b);
    printf("乘法: %d * %d = %d\n", a, b, a * b);
    printf("除法: %d / %d = %d\n", a, b, a / b);
    printf("取餘數: %d %% %d = %d\n", a, b, a % b);
    return 0;
}
```
**解釋**：
- `+`、`-`、`*`、`/`、`%` 分別是加、減、乘、除與取餘數運算。
- `%` 取餘數運算只能用於整數。

---

### **範例 2：使用 `float` 進行小數計算**
```c
#include <stdio.h>

int main() {
    float a = 10.0, b = 3.0;
    printf("加法: %.2f + %.2f = %.2f\n", a, b, a + b);
    printf("減法: %.2f - %.2f = %.2f\n", a, b, a - b);
    printf("乘法: %.2f * %.2f = %.2f\n", a, b, a * b);
    printf("除法: %.2f / %.2f = %.2f\n", a, b, a / b);
    return 0;
}
```
**解釋**：
- 使用 `float` 變數可以進行小數計算。
- `%.2f` 格式化輸出，表示顯示兩位小數。

---

### **範例 3：輸入兩個數並進行計算**
```c
#include <stdio.h>

int main() {
    int x, y;
    printf("請輸入兩個整數: ");
    scanf("%d %d", &x, &y);
    printf("加法: %d + %d = %d\n", x, y, x + y);
    printf("減法: %d - %d = %d\n", x, y, x - y);
    printf("乘法: %d * %d = %d\n", x, y, x * y);
    printf("除法: %d / %d = %d\n", x, y, x / y);
    printf("取餘數: %d %% %d = %d\n", x, y, x % y);
    return 0;
}
```
**解釋**：
- `scanf("%d %d", &x, &y);` 允許用戶輸入兩個整數。
- 計算輸入的數值並輸出結果。

---

### **範例 4：避免整數除法錯誤**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    float result = (float)a / b;
    printf("正確的除法結果: %.2f\n", result);
    return 0;
}
```
**解釋**：
- `a / b` 如果 `a` 和 `b` 都是 `int`，則結果也是 `int`，會自動去掉小數部分。
- `(float)a / b` 讓 `a` 轉換為 `float`，確保結果是小數。

---

### **範例 5：運算優先順序**
```c
#include <stdio.h>

int main() {
    int result = 10 + 2 * 5;
    printf("10 + 2 * 5 = %d\n", result);
    result = (10 + 2) * 5;
    printf("(10 + 2) * 5 = %d\n", result);
    return 0;
}
```
**解釋**：
- 運算優先順序遵循數學規則：`*` 乘法比 `+` 加法優先。
- `()` 括號可改變運算順序。

---

### **範例 6：自增 (`++`) 和自減 (`--`) 運算**
```c
#include <stdio.h>

int main() {
    int x = 5;
    printf("x = %d\n", x);
    printf("x++ = %d\n", x++);
    printf("現在 x = %d\n", x);
    printf("++x = %d\n", ++x);
    return 0;
}
```
**解釋**：
- `x++` (後置遞增)：先使用 `x`，再增加 1。
- `++x` (前置遞增)：先增加 1，再使用 `x`。

---

### **範例 7：計算平方和立方**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數: ");
    scanf("%d", &num);
    printf("平方: %d\n", num * num);
    printf("立方: %d\n", num * num * num);
    return 0;
}
```
**解釋**：
- `num * num` 計算平方。
- `num * num * num` 計算立方。

---

### **範例 8：使用 `math.h` 進行高級運算**
```c
#include <stdio.h>
#include <math.h>

int main() {
    double num;
    printf("請輸入一個數: ");
    scanf("%lf", &num);
    printf("平方根: %.2f\n", sqrt(num));
    printf("次方 (2^3): %.2f\n", pow(2, 3));
    return 0;
}
```
**解釋**：
- `sqrt(num)` 計算平方根。
- `pow(a, b)` 計算 `a^b`。

---

這些範例涵蓋了基本算術運算，你可以試著執行看看！如果沒問題，我們可以進入下一個單元 **邏輯運算 (Logical Operation)** 🚀

好的！我們現在來學習 **邏輯運算 (Logical Operation)**，這是程式設計中判斷條件時必須使用的運算，通常與 **條件判斷** (`if`、`while`、`for`) 一起使用。

---

## **邏輯運算 (Logical Operation)**
C 語言提供 3 種邏輯運算符號：

| 運算符號 | 名稱 | 說明 |
|---------|------|------|
| `&&` | AND (且) | 兩個條件都為 `true`，結果才是 `true` |
| `||` | OR (或) | 其中一個條件為 `true`，結果就是 `true` |
| `!` | NOT (否定) | 反轉條件，`true` 變 `false`，`false` 變 `true` |

邏輯運算通常與 **關係運算符** (`==`, `!=`, `>`, `<`, `>=`, `<=`) 一起使用。

---

### **範例 1：使用 `&&` (AND)**
```c
#include <stdio.h>

int main() {
    int a = 5, b = 10;
    if (a > 0 && b > 0) {
        printf("a 和 b 都是正數\n");
    }
    return 0;
}
```
**解釋**：
- `a > 0 && b > 0`：`a` 和 `b` 兩個條件都要成立，`printf` 才會執行。

---

### **範例 2：使用 `||` (OR)**
```c
#include <stdio.h>

int main() {
    int a = -5, b = 10;
    if (a > 0 || b > 0) {
        printf("至少有一個是正數\n");
    }
    return 0;
}
```
**解釋**：
- `a > 0 || b > 0`：只要 **一個條件成立**，程式就會輸出 `"至少有一個是正數"`。

---

### **範例 3：使用 `!` (NOT)**
```c
#include <stdio.h>

int main() {
    int isSunny = 0; // 0 代表「不是晴天」
    if (!isSunny) {
        printf("今天不是晴天\n");
    }
    return 0;
}
```
**解釋**：
- `!isSunny` 會將 `0` 變成 `1`，所以 `if` 條件成立，輸出 `"今天不是晴天"`。

---

### **範例 4：判斷是否在範圍內**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數字: ");
    scanf("%d", &num);

    if (num >= 1 && num <= 100) {
        printf("數字在 1 到 100 之間\n");
    } else {
        printf("數字不在範圍內\n");
    }
    return 0;
}
```
**解釋**：
- `num >= 1 && num <= 100`：只有當 `num` 在 `1` 到 `100` 之間，才會輸出 `"數字在 1 到 100 之間"`。

---

### **範例 5：判斷是否為閏年**
```c
#include <stdio.h>

int main() {
    int year;
    printf("請輸入年份: ");
    scanf("%d", &year);

    if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0) {
        printf("%d 是閏年\n", year);
    } else {
        printf("%d 不是閏年\n", year);
    }
    return 0;
}
```
**解釋**：
- **閏年規則**：
  - 能被 4 整除，**但不能** 被 100 整除 (`year % 4 == 0 && year % 100 != 0`)。
  - 或者能被 400 整除 (`year % 400 == 0`)。

---

### **範例 6：登入系統 (密碼驗證)**
```c
#include <stdio.h>

int main() {
    int password;
    printf("請輸入密碼: ");
    scanf("%d", &password);

    if (password == 1234) {
        printf("登入成功\n");
    } else {
        printf("密碼錯誤\n");
    }
    return 0;
}
```
**解釋**：
- `password == 1234`：若密碼正確，顯示 `"登入成功"`，否則顯示 `"密碼錯誤"`。

---

### **範例 7：判斷是否為偶數**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數字: ");
    scanf("%d", &num);

    if (num % 2 == 0) {
        printf("%d 是偶數\n", num);
    } else {
        printf("%d 是奇數\n", num);
    }
    return 0;
}
```
**解釋**：
- `num % 2 == 0`：判斷 `num` 是否能被 2 整除，決定是偶數或奇數。

---

### **範例 8：三數最大值**
```c
#include <stdio.h>

int main() {
    int a, b, c, max;
    printf("請輸入三個數字: ");
    scanf("%d %d %d", &a, &b, &c);

    max = (a > b && a > c) ? a : (b > c ? b : c);
    printf("最大值是: %d\n", max);
    return 0;
}
```
**解釋**：
- 使用三元運算子 (`? :`) 判斷 `a`、`b`、`c` 誰最大。

---

### **範例 9：密碼三次輸入機會**
```c
#include <stdio.h>

int main() {
    int password, attempts = 3;
    
    while (attempts > 0) {
        printf("請輸入密碼: ");
        scanf("%d", &password);

        if (password == 1234) {
            printf("登入成功\n");
            return 0; // 結束程式
        } else {
            attempts--;
            printf("密碼錯誤，剩餘嘗試次數: %d\n", attempts);
        }
    }
    
    printf("登入失敗，請稍後再試\n");
    return 0;
}
```
**解釋**：
- 使用 `while` 迴圈讓用戶有 **3 次機會** 輸入正確密碼。
- 若密碼錯誤，則顯示剩餘嘗試次數。

---

這些範例涵蓋了邏輯運算的基礎與應用，你可以試著執行看看！  
如果沒問題，我們可以進入下一個單元 **位元運算 (Bitwise Operation)** 🚀

好的！我們現在來學習 **位元運算 (Bitwise Operation)**，這是 C 語言的低階運算之一，在處理效能要求高的應用 (如嵌入式系統、加密演算法、效能最佳化) 非常有用。  

---

## **位元運算 (Bitwise Operation)**
位元運算是直接對 **二進位** 進行運算的方式，C 語言提供以下幾種位元運算符號：

| 運算符號 | 名稱 | 說明 |
|---------|------|------|
| `&` | AND (位元與) | 兩個位元都為 `1`，結果才是 `1` |
| `|` | OR (位元或) | 只要有一個位元為 `1`，結果就是 `1` |
| `^` | XOR (位元異或) | 兩個位元不同時，結果為 `1` |
| `~` | NOT (位元反轉) | 反轉所有位元 (`0` 變 `1`，`1` 變 `0`) |
| `<<` | 左移 | 向左移動位元，**低位補 0**，等於 `×2` |
| `>>` | 右移 | 向右移動位元，視情況補 `0` 或 `1`，等於 `/2` |

> **補充**：  
> - `<<` (左移) 相當於乘以 `2` 的次方 (`x << n` 相當於 `x * 2^n`)  
> - `>>` (右移) 相當於除以 `2` 的次方 (`x >> n` 相當於 `x / 2^n`)  

---

### **範例 1：基本位元運算**
```c
#include <stdio.h>

int main() {
    int a = 5, b = 3;
    
    printf("a & b = %d\n", a & b); // AND 運算
    printf("a | b = %d\n", a | b); // OR 運算
    printf("a ^ b = %d\n", a ^ b); // XOR 運算
    printf("~a = %d\n", ~a);       // NOT 運算
    return 0;
}
```
**解釋** (二進位表示)：
```
a = 5  ->  00000101
b = 3  ->  00000011
-------------------
a & b  ->  00000001  (結果為 1)
a | b  ->  00000111  (結果為 7)
a ^ b  ->  00000110  (結果為 6)
~a     ->  11111010  (補數表示 -6)
```

---

### **範例 2：位元左移 (`<<`)**
```c
#include <stdio.h>

int main() {
    int num = 5;
    printf("5 << 1 = %d\n", num << 1); // 左移 1 位
    printf("5 << 2 = %d\n", num << 2); // 左移 2 位
    return 0;
}
```
**解釋**：
```
5 = 00000101
5 << 1 = 00001010  (10)
5 << 2 = 00010100  (20)
```
- `num << 1` 相當於 `num * 2`
- `num << 2` 相當於 `num * 4`

---

### **範例 3：位元右移 (`>>`)**
```c
#include <stdio.h>

int main() {
    int num = 20;
    printf("20 >> 1 = %d\n", num >> 1); // 右移 1 位
    printf("20 >> 2 = %d\n", num >> 2); // 右移 2 位
    return 0;
}
```
**解釋**：
```
20 = 00010100
20 >> 1 = 00001010  (10)
20 >> 2 = 00000101  (5)
```
- `num >> 1` 相當於 `num / 2`
- `num >> 2` 相當於 `num / 4`

---

### **範例 4：判斷奇數或偶數 (利用 `&` 運算)**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數字: ");
    scanf("%d", &num);

    if (num & 1)
        printf("%d 是奇數\n", num);
    else
        printf("%d 是偶數\n", num);

    return 0;
}
```
**解釋**：
- `num & 1` 只會檢查 `num` 的最後一位：
  - `1` (奇數) -> `00000001`
  - `0` (偶數) -> `00000000`

---

### **範例 5：使用 `XOR` 交換兩數**
```c
#include <stdio.h>

int main() {
    int a = 5, b = 3;

    printf("交換前: a = %d, b = %d\n", a, b);
    a = a ^ b;
    b = a ^ b;
    a = a ^ b;
    printf("交換後: a = %d, b = %d\n", a, b);

    return 0;
}
```
**解釋**：
- `a = a ^ b`
- `b = a ^ b`
- `a = a ^ b`
  
這樣可以不使用額外變數來交換 `a` 和 `b` 的值。

---

### **範例 6：設定與清除特定位元**
```c
#include <stdio.h>

int main() {
    int num = 8; // 00001000

    // 設定第 1 位為 1 (| 運算)
    num = num | (1 << 1);
    printf("設定後: %d\n", num);

    // 清除第 3 位為 0 (& 運算)
    num = num & ~(1 << 3);
    printf("清除後: %d\n", num);

    return 0;
}
```
**解釋**：
- `num | (1 << 1)`：設定某個位元 (`num` OR `00000010`)
- `num & ~(1 << 3)`：清除某個位元 (`num` AND `11110111`)

---

### **範例 7：檢查某個位元是否為 1**
```c
#include <stdio.h>

int main() {
    int num = 10; // 00001010
    int pos = 3;

    if (num & (1 << pos)) {
        printf("第 %d 位是 1\n", pos);
    } else {
        printf("第 %d 位是 0\n", pos);
    }

    return 0;
}
```
**解釋**：
- `num & (1 << pos)` 檢查 `num` 的第 `pos` 位是否為 `1`。

---

### **範例 8：計算某數的二進位 1 的數量**
```c
#include <stdio.h>

int main() {
    int num, count = 0;
    printf("請輸入一個數: ");
    scanf("%d", &num);

    while (num) {
        count += num & 1;
        num >>= 1;
    }

    printf("二進位中 1 的數量: %d\n", count);
    return 0;
}
```
**解釋**：
- 每次用 `num & 1` 判斷最右邊的位元是否為 `1`，並右移 `num`。

---

這些範例涵蓋了 **位元運算** 的基礎與應用，你可以試著執行看看！  
如果沒問題，我們可以進入下一個單元 **條件判斷與迴圈 (Conditional Expressions and Loop)** 🚀

好的！現在我們來學習 **條件判斷與迴圈 (Conditional Expressions and Loop)**，這是 C 語言中控制程式流程的重要工具，能夠根據條件執行不同的程式碼，或重複執行某段程式碼。

---

## **條件判斷 (Conditional Statements)**  
C 語言的條件判斷主要有：
1. `if` 條件判斷
2. `if-else` 條件判斷
3. `if-else if-else` 多重條件判斷
4. `switch-case` 敘述

---

### **範例 1：基本 `if` 條件判斷**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數字: ");
    scanf("%d", &num);

    if (num > 0) {
        printf("這是正數\n");
    }

    return 0;
}
```
**解釋**：
- 當 `num > 0` 時，執行 `printf("這是正數\n");`
- 否則，程式直接結束。

---

### **範例 2：`if-else` 條件判斷**
```c
#include <stdio.h>

int main() {
    int num;
    printf("請輸入一個數字: ");
    scanf("%d", &num);

    if (num % 2 == 0) {
        printf("%d 是偶數\n", num);
    } else {
        printf("%d 是奇數\n", num);
    }

    return 0;
}
```
**解釋**：
- `num % 2 == 0` 為真時，顯示 `偶數`，否則顯示 `奇數`。

---

### **範例 3：`if-else if-else` 多重條件判斷**
```c
#include <stdio.h>

int main() {
    int score;
    printf("請輸入分數: ");
    scanf("%d", &score);

    if (score >= 90) {
        printf("等級: A\n");
    } else if (score >= 80) {
        printf("等級: B\n");
    } else if (score >= 70) {
        printf("等級: C\n");
    } else {
        printf("等級: D\n");
    }

    return 0;
}
```
**解釋**：
- `if` 和 `else if` 可用來處理多種條件。

---

### **範例 4：`switch-case` 判斷**
```c
#include <stdio.h>

int main() {
    int day;
    printf("請輸入星期 (1-7): ");
    scanf("%d", &day);

    switch (day) {
        case 1:
            printf("星期一\n");
            break;
        case 2:
            printf("星期二\n");
            break;
        case 3:
            printf("星期三\n");
            break;
        case 4:
            printf("星期四\n");
            break;
        case 5:
            printf("星期五\n");
            break;
        case 6:
        case 7:
            printf("週末\n");
            break;
        default:
            printf("輸入錯誤\n");
    }

    return 0;
}
```
**解釋**：
- `switch-case` 適合用來處理固定選項的條件判斷，如選單或星期。

---

## **迴圈 (Loop)**
C 語言提供以下 3 種迴圈：
1. `for` 迴圈
2. `while` 迴圈
3. `do-while` 迴圈

---

### **範例 5：`for` 迴圈**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        printf("目前 i = %d\n", i);
    }

    return 0;
}
```
**解釋**：
- `for (起始值; 條件; 增減)`  
- `i = 1` 開始，每次執行 `i++`，直到 `i > 5` 停止。

---

### **範例 6：`while` 迴圈**
```c
#include <stdio.h>

int main() {
    int count = 1;
    
    while (count <= 5) {
        printf("目前 count = %d\n", count);
        count++;
    }

    return 0;
}
```
**解釋**：
- `while (條件)`：當 `條件` 為真時，執行迴圈內容。

---

### **範例 7：`do-while` 迴圈**
```c
#include <stdio.h>

int main() {
    int num;
    
    do {
        printf("請輸入大於 0 的數字: ");
        scanf("%d", &num);
    } while (num <= 0);

    printf("你輸入的數字是: %d\n", num);
    return 0;
}
```
**解釋**：
- `do-while` 迴圈至少執行一次，即使條件不成立。

---

### **範例 8：計算 1 到 N 的總和**
```c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("請輸入 N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++) {
        sum += i;
    }

    printf("1 到 %d 的總和是: %d\n", n, sum);
    return 0;
}
```
**解釋**：
- 使用 `for` 迴圈來累加 `1 + 2 + ... + n`。

---

### **範例 9：找出 1 到 100 之間的偶數**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 100; i++) {
        if (i % 2 == 0) {
            printf("%d ", i);
        }
    }

    return 0;
}
```
**解釋**：
- `if (i % 2 == 0)` 判斷 `i` 是否為偶數。

---

### **範例 10：使用 `break` 和 `continue`**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i == 5) {
            printf("遇到 5，跳出迴圈\n");
            break;
        }
        if (i % 2 == 0) {
            continue;
        }
        printf("%d ", i);
    }

    return 0;
}
```
**解釋**：
- `break;` 會立即跳出迴圈。
- `continue;` 會跳過本次迴圈剩下的程式碼，直接進入下一次迴圈。

---

這些範例涵蓋了 **條件判斷** 和 **迴圈** 的基礎與應用，你可以試著執行看看！  
如果沒問題，我們可以進入下一個單元 **陣列與結構 (Arrays and Structures)** 🚀

好的！現在我們來學習 **陣列與結構 (Arrays and Structures)**，這是 C 語言中用來存儲多個值的重要概念，能夠讓程式更高效地處理資料。  

---

# **🔹 陣列 (Array)**  
陣列是 **相同類型** 的 **一組變數**，它們被存放在**連續的記憶體位置**中，並使用索引 (index) 來存取。  

## **📌 陣列的基本語法**
```c
資料型態 陣列名稱[大小];
```
例如：
```c
int numbers[5]; // 宣告 5 個整數的陣列
```

---

### **範例 1：宣告與初始化陣列**
```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50}; // 初始化陣列

    printf("第一個元素: %d\n", numbers[0]);
    printf("第三個元素: %d\n", numbers[2]);
    
    return 0;
}
```
**解釋**：
- 陣列 `numbers` 共有 **5 個整數元素**，索引從 `0` 開始 (`numbers[0]` 是第一個元素)。

---

### **範例 2：使用 `for` 迴圈輸出陣列**
```c
#include <stdio.h>

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};

    for (int i = 0; i < 5; i++) {
        printf("numbers[%d] = %d\n", i, numbers[i]);
    }

    return 0;
}
```
**解釋**：
- `for` 迴圈讓我們遍歷陣列中的所有元素。

---

### **範例 3：輸入與計算陣列總和**
```c
#include <stdio.h>

int main() {
    int numbers[5], sum = 0;

    printf("請輸入 5 個數字:\n");
    for (int i = 0; i < 5; i++) {
        scanf("%d", &numbers[i]);
        sum += numbers[i]; // 計算總和
    }

    printf("總和為: %d\n", sum);
    return 0;
}
```
**解釋**：
- 使用 `scanf` 讓使用者輸入陣列值，並計算總和。

---

### **範例 4：找出陣列中的最大值**
```c
#include <stdio.h>

int main() {
    int numbers[5] = {15, 9, 30, 25, 18};
    int max = numbers[0];

    for (int i = 1; i < 5; i++) {
        if (numbers[i] > max) {
            max = numbers[i];
        }
    }

    printf("最大值是: %d\n", max);
    return 0;
}
```
**解釋**：
- 假設 `numbers[0]` 是最大值，遍歷陣列，若找到更大值則更新 `max`。

---

### **範例 5：二維陣列 (矩陣)**
```c
#include <stdio.h>

int main() {
    int matrix[2][3] = { {1, 2, 3}, {4, 5, 6} };

    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 3; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
**解釋**：
- `matrix[2][3]` 表示有 2 列 3 欄的矩陣，使用巢狀 `for` 迴圈輸出內容。

---

# **🔹 結構 (Structure)**
結構 (`struct`) 是 **自定義資料型態**，可以組合不同類型的變數到同一個物件中，類似 C++ 的 `class` (但沒有方法)。

## **📌 結構的基本語法**
```c
struct 結構名稱 {
    資料型態 成員1;
    資料型態 成員2;
    ...
};
```

---

### **範例 6：宣告結構與存取**
```c
#include <stdio.h>

// 定義結構
struct Student {
    char name[20];
    int age;
    float score;
};

int main() {
    struct Student s1 = {"Alice", 18, 92.5};

    printf("姓名: %s\n", s1.name);
    printf("年齡: %d\n", s1.age);
    printf("分數: %.1f\n", s1.score);

    return 0;
}
```
**解釋**：
- `struct Student` 是學生資料型態，包含 `name`、`age`、`score` 三個欄位。
- `s1` 是一個學生變數，並存有 Alice 的資料。

---

### **範例 7：使用 `scanf` 讓使用者輸入結構資料**
```c
#include <stdio.h>

struct Student {
    char name[20];
    int age;
    float score;
};

int main() {
    struct Student s;

    printf("請輸入姓名: ");
    scanf("%s", s.name);
    printf("請輸入年齡: ");
    scanf("%d", &s.age);
    printf("請輸入分數: ");
    scanf("%f", &s.score);

    printf("學生資料: %s, 年齡: %d, 分數: %.1f\n", s.name, s.age, s.score);
    
    return 0;
}
```
**解釋**：
- 讓使用者輸入 `name`、`age`、`score`，並顯示輸入的結果。

---

### **範例 8：結構陣列 (儲存多名學生資料)**
```c
#include <stdio.h>

struct Student {
    char name[20];
    int age;
    float score;
};

int main() {
    struct Student students[3] = {
        {"Alice", 18, 90.5},
        {"Bob", 19, 85.0},
        {"Charlie", 17, 78.5}
    };

    for (int i = 0; i < 3; i++) {
        printf("學生 %d: %s, 年齡: %d, 分數: %.1f\n", i+1, students[i].name, students[i].age, students[i].score);
    }

    return 0;
}
```
**解釋**：
- `students[3]` 是一個結構陣列，能存放 3 名學生的資料。

---

### **範例 9：使用指標存取結構**
```c
#include <stdio.h>

struct Student {
    char name[20];
    int age;
    float score;
};

int main() {
    struct Student s = {"David", 20, 88.5};
    struct Student *ptr = &s; // 指標指向結構變數

    printf("姓名: %s\n", ptr->name);
    printf("年齡: %d\n", ptr->age);
    printf("分數: %.1f\n", ptr->score);

    return 0;
}
```
**解釋**：
- `ptr->name` 是 `(*ptr).name` 的簡寫方式，用來存取結構成員。

---

這些範例涵蓋了 **陣列** 和 **結構** 的基礎與應用，你可以試著執行看看！  
如果沒問題，我們可以進入下一個單元 **字元與字串 (Character and String)** 🚀


好的！現在我們來學習 **字元與字串 (Character and String)**，這是 C 語言處理文字資料的重要部分。

---

# **🔹 字元 (Character)**
在 C 語言中，字元 (`char`) 是一種基本資料型態，用來儲存單個字元。

## **📌 字元的基本語法**
```c
char 變數名稱 = '字元';
```
- **字元必須使用單引號 `' '` 包住**，例如：
  ```c
  char letter = 'A';
  ```
- 字元在內部實際上是 **數字 (ASCII 值)**，例如：
  - `'A'` 的 ASCII 值是 `65`
  - `'a'` 的 ASCII 值是 `97`
  - `'0'` 的 ASCII 值是 `48`

---

### **範例 1：輸出字元與對應的 ASCII 值**
```c
#include <stdio.h>

int main() {
    char ch = 'A';
    
    printf("字元: %c\n", ch);
    printf("ASCII 值: %d\n", ch);

    return 0;
}
```
**解釋**：
- `%c` 用於輸出字元，`%d` 用於輸出字元的 ASCII 數值。

---

### **範例 2：判斷字元是大寫還是小寫**
```c
#include <stdio.h>

int main() {
    char ch;
    printf("請輸入一個字元: ");
    scanf("%c", &ch);

    if (ch >= 'A' && ch <= 'Z') {
        printf("這是大寫字母\n");
    } else if (ch >= 'a' && ch <= 'z') {
        printf("這是小寫字母\n");
    } else {
        printf("這不是字母\n");
    }

    return 0;
}
```
**解釋**：
- 利用 ASCII 值的範圍來判斷字元類型。

---

# **🔹 字串 (String)**
字串在 C 語言中是 **字元陣列** (`char array`)，並且**結尾必須有 `'\0'` (空字元)** 來標記字串的結束。

## **📌 字串的基本語法**
```c
char 字串變數[大小] = "字串內容";
```
或
```c
char 字串變數[] = {'字', '串', '\0'};
```
**範例：**
```c
char name[] = "Alice"; // 自動加上 '\0'
char name2[] = {'A', 'l', 'i', 'c', 'e', '\0'};
```
---

### **範例 3：字串的輸出**
```c
#include <stdio.h>

int main() {
    char name[] = "Alice";

    printf("名字: %s\n", name);
    
    return 0;
}
```
**解釋**：
- `%s` 用來輸出字串。

---

### **範例 4：輸入字串**
```c
#include <stdio.h>

int main() {
    char name[20];

    printf("請輸入名字: ");
    scanf("%s", name); // 注意: scanf 不能讀取空格
    printf("你輸入的名字是: %s\n", name);

    return 0;
}
```
**⚠ 注意：**  
- `scanf("%s", name);` **不能輸入包含空格的字串**，如 `"John Doe"` 會只讀取 `"John"`。

---

### **範例 5：使用 `gets()` 讀取包含空格的字串**
```c
#include <stdio.h>

int main() {
    char name[50];

    printf("請輸入你的全名: ");
    fgets(name, sizeof(name), stdin); // fgets 允許輸入空格
    printf("你的全名是: %s\n", name);

    return 0;
}
```
**解釋**：
- `fgets(name, sizeof(name), stdin);` 可以輸入 **包含空格的字串**。

---

### **範例 6：計算字串長度**
```c
#include <stdio.h>
#include <string.h> // 必須引入 string.h

int main() {
    char word[] = "Hello";
    
    int length = strlen(word);
    printf("字串長度: %d\n", length);

    return 0;
}
```
**解釋**：
- `strlen(字串變數)` 取得字串長度，但 **不包含 `\0`**。

---

### **範例 7：字串比較**
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[] = "apple";
    char str2[] = "banana";

    if (strcmp(str1, str2) == 0) {
        printf("兩個字串相等\n");
    } else {
        printf("兩個字串不相等\n");
    }

    return 0;
}
```
**解釋**：
- `strcmp(str1, str2)` 比較 `str1` 和 `str2`：
  - **回傳 0** 表示相等
  - **回傳負數** 表示 `str1` < `str2`
  - **回傳正數** 表示 `str1` > `str2`

---

### **範例 8：字串拼接**
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str1[20] = "Hello, ";
    char str2[] = "World!";

    strcat(str1, str2); // 字串拼接
    printf("%s\n", str1);

    return 0;
}
```
**解釋**：
- `strcat(str1, str2);` 把 `str2` **加到 `str1` 後面**。

---

### **範例 9：將小寫轉換為大寫**
```c
#include <stdio.h>
#include <ctype.h> // 必須引入 ctype.h

int main() {
    char str[] = "hello";

    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = toupper(str[i]); // 轉換為大寫
    }

    printf("轉換後: %s\n", str);
    
    return 0;
}
```
**解釋**：
- `toupper(ch)` 轉換 **小寫字母** 為 **大寫字母**。

---

### **範例 10：反轉字串**
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello";
    int len = strlen(str);

    for (int i = 0; i < len / 2; i++) {
        char temp = str[i];
        str[i] = str[len - i - 1];
        str[len - i - 1] = temp;
    }

    printf("反轉後的字串: %s\n", str);

    return 0;
}
```
**解釋**：
- 使用 `strlen(str)` 取得字串長度，然後交換對應位置的字元來反轉字串。

---

這些範例涵蓋了 **字元與字串** 的基礎與應用，你可以試著執行看看！  
如果沒問題，我們可以進入下一個單元 **函數呼叫與遞迴 (Function Call and Recursion)** 🚀

好的！現在我們來學習 **函數呼叫與遞迴 (Function Call and Recursion)**，這是 C 語言中組織程式碼的重要概念。  

---

# **🔹 函數呼叫 (Function Call)**
函數可以將程式碼模組化，使其更容易維護與重複使用。

## **📌 函數的基本語法**
```c
返回型態 函數名稱(參數類型 參數1, 參數類型 參數2, ... ) {
    // 函數內容
    return 值;  // (若非 void，則須回傳值)
}
```

**範例：**
```c
#include <stdio.h>

// 函數宣告
int add(int a, int b);

int main() {
    int result = add(3, 5); // 呼叫函數
    printf("結果: %d\n", result);
    return 0;
}

// 函數定義
int add(int a, int b) {
    return a + b;
}
```
**解釋**：
- `int add(int a, int b)` 定義了一個回傳整數的函數 `add`，將 `a` 和 `b` 相加後回傳。
- `int result = add(3, 5);` 呼叫函數並接收回傳值。

---

### **範例 1：計算平方值**
```c
#include <stdio.h>

// 計算平方值的函數
int square(int num) {
    return num * num;
}

int main() {
    int x = 4;
    printf("%d 的平方是 %d\n", x, square(x));
    return 0;
}
```
**解釋**：
- `square(int num)` 接受一個整數，回傳其平方值。

---

### **範例 2：函數傳遞陣列**
```c
#include <stdio.h>

// 計算陣列總和
int sumArray(int arr[], int size) {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];
    }
    return sum;
}

int main() {
    int numbers[] = {1, 2, 3, 4, 5};
    int total = sumArray(numbers, 5);
    printf("陣列總和: %d\n", total);
    return 0;
}
```
**解釋**：
- 陣列作為參數時，不需要 `[]`，但要傳遞大小資訊。

---

### **範例 3：傳值與傳址 (Call by Value vs. Call by Reference)**
```c
#include <stdio.h>

// 傳值 (值不變)
void passByValue(int x) {
    x = 10;
}

// 傳址 (值改變)
void passByReference(int *x) {
    *x = 10;
}

int main() {
    int a = 5, b = 5;

    passByValue(a);
    printf("傳值後 a: %d\n", a);  // a 不變

    passByReference(&b);
    printf("傳址後 b: %d\n", b);  // b 改變

    return 0;
}
```
**解釋**：
- `passByValue(int x)` 只修改 `x` 的副本，`a` 不變。
- `passByReference(int *x)` 使用指標修改原變數，`b` 被改變。

---

# **🔹 遞迴 (Recursion)**
遞迴函數是**自己呼叫自己的函數**，適用於**分解問題的情境**。

## **📌 遞迴函數的基本語法**
```c
返回型態 函數名稱(參數) {
    if (終止條件) return 結果;
    return 函數名稱(新的參數);
}
```
**關鍵點**：
- **一定要有終止條件**，否則會無限遞迴導致程式崩潰。

---

### **範例 4：階乘 (Factorial)**
```c
#include <stdio.h>

// 計算 n! (n 階乘)
int factorial(int n) {
    if (n == 0) return 1;  // 終止條件
    return n * factorial(n - 1);
}

int main() {
    int num = 5;
    printf("%d 的階乘是 %d\n", num, factorial(num));
    return 0;
}
```
**解釋**：
- `factorial(5) = 5 * factorial(4)`
- `factorial(4) = 4 * factorial(3)`
- 直到 `factorial(0) = 1` 終止遞迴。

---

### **範例 5：費氏數列 (Fibonacci Sequence)**
```c
#include <stdio.h>

// 計算 Fibonacci 數列
int fibonacci(int n) {
    if (n == 0) return 0;
    if (n == 1) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n = 6;
    printf("第 %d 項 Fibonacci 數: %d\n", n, fibonacci(n));
    return 0;
}
```
**解釋**：
- `fibonacci(6) = fibonacci(5) + fibonacci(4)`
- `fibonacci(5) = fibonacci(4) + fibonacci(3)`
- 直到 `fibonacci(0) = 0` 和 `fibonacci(1) = 1` 終止遞迴。

---

### **範例 6：遞迴計算次方**
```c
#include <stdio.h>

// 計算 base^exp
int power(int base, int exp) {
    if (exp == 0) return 1;  // 任何數的 0 次方是 1
    return base * power(base, exp - 1);
}

int main() {
    printf("2 的 5 次方: %d\n", power(2, 5));
    return 0;
}
```
**解釋**：
- `power(2,5) = 2 * power(2,4)`
- 直到 `power(2,0) = 1` 終止遞迴。

---

### **範例 7：遞迴反轉字串**
```c
#include <stdio.h>
#include <string.h>

// 遞迴函數來反轉字串
void reverseString(char str[], int start, int end) {
    if (start >= end) return;  // 終止條件

    // 交換字元
    char temp = str[start];
    str[start] = str[end];
    str[end] = temp;

    reverseString(str, start + 1, end - 1); // 遞迴呼叫
}

int main() {
    char str[] = "hello";
    reverseString(str, 0, strlen(str) - 1);
    printf("反轉後的字串: %s\n", str);
    return 0;
}
```
**解釋**：
- 透過遞迴交換字串兩端的字元，直到 `start >= end` 終止遞迴。

---

這些範例涵蓋了 **函數呼叫** 和 **遞迴** 的基礎與應用，你可以試著執行看看！  
如果沒問題，恭喜你完成所有單元！🎉 🚀  
