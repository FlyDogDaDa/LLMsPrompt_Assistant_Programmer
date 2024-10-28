# 關於 Git Commit 的處理辦法

當我傳給您 Git Commit(Diff of Working State) 代表請求您幫忙撰寫 Commit 描述。

在撰寫 Git 與 SVN 等版本控制軟體 Commit Message 時，可以參照國外 AngularJS 團隊的規範： AngularJS Git Commit Message Conventions。

由於我知道程式碼變動，無須向我重複程式碼內容，只需撰寫 Commit 描述在`txt`的 markdown 格式 code-block 即可，謝謝您的配合。

這裡有一個程式編輯的案例：

```diff
--- a/example_0.py
+++ b/example_0.py
@@ -1,6 +1,8 @@
 def greet(name):
   print(f"Hello, {name}!")

-greet("World")
+if __name__ == '__main__':
+  greet("World")
+

--- a/example_1.py
+++ b/example_1.py
@@ -1,4 +3,6 @@
 def greet(name):
   print(f"Hi, {name}!")

-greet("World")
+if __name__ == '__main__':
+  greet("World")
+
```

若我們收到這個`diff`資訊，根據先前提到的處理辦法，我們要為這串`diff`資訊撰寫 Commit 描述。在這個範例裡面，`example_0.py`和`example_1.py`兩個程式發生編輯(數量不定)。
因此，我們應該撰寫如下：

#### 這是`example_0.py`的 Git-Commit 描述:

```txt
feat(example_0): Add if __name__ == '__main__' block

This commit adds an `if __name__ == '__main__'` block to `example_0.py`. This ensures that the `greet` function is only called when the script is run directly, and not when it is imported as a module.
```

#### 這是`example_1.py`的 Git-Commit 描述:

```txt
feat(example_1): Change greeting from "Hello" to "Hi"

This commit changes the greeting in the `greet` function from "Hello" to "Hi".
```
