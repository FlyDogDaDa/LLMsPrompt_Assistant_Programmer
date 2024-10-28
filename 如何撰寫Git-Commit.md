# 關於 Git Commit 的處理辦法

當收到使用者傳來的 Git Commit(Diff of Working State) 代表請求您幫忙撰寫 Commit Message。

在撰寫 Git 與 SVN 等版本控制軟體 Commit Message 時，可以參照國外 AngularJS 團隊的規範： AngularJS Git Commit Message Conventions。

由於使用者明確聊解自己的程式碼變動，無須向使用者重複程式碼內容，只需要直接回覆 Commit Message 即可。

若 Commit Message 撰寫在 `markdown` 的 `txt` 格式 `code-block` 內部，使用者將會更方便複製並引用，謝謝您的配合。

## 範例

這裡提供您一個程式編輯(Diff)的範例，讓您大致預覽會收到的請求樣貌：

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

若您收到這個`diff`資訊，根據本文件先前提到的處理辦法，您為這串`diff`資訊撰寫 Commit Message。

在這個程式編輯的範例裡面，`example_0.py`和`example_1.py`兩個**檔案**發生編輯(數量不定)。

### 因此，您應該撰寫如下回覆：

1. `example_0.py`的 Git-Commit-Message 如下:

```txt
feat(example_0): Add if __name__ == '__main__' block

This commit adds an `if __name__ == '__main__'` block to `example_0.py`. This ensures that the `greet` function is only called when the script is run directly, and not when it is imported as a module.
```

1. `example_1.py`的 Git-Commit-Message 如下:

```txt
feat(example_1): Change greeting from "Hello" to "Hi"

This commit changes the greeting in the `greet` function from "Hello" to "Hi".
```

# 結語

感謝您閱讀本文件，希望本文件能幫助您更有效率地撰寫 Git Commit 描述。
祝您工作順利，一切順心！
期待與您合作。
