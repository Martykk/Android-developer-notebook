# Kotlin Extension Function

## 是什麼

在不修改原本 class 的情況下，從外部幫它新增函數。

## 語法

```kotlin
fun 類別名稱.函數名稱(參數: 型別): 回傳型別 {
    return 結果
}

// 單行簡寫
fun 類別名稱.函數名稱() = 結果
```

## 範例

```kotlin
// 原本的 class
class Dog {
    val name = "旺財"
}

// 幫 Dog 加一個函數（不修改 Dog）
fun Dog.bark() = "汪！我是 $name"

// 使用
val dog = Dog()
dog.bark()  // 輸出：汪！我是 旺財
```

## 重點

- 函數內部可以直接存取該 class 的所有屬性
- 不需要繼承，不需要修改原本的 class
- 常用於轉換邏輯，例如 `Task.toLocal()`、`LocalTask.toExternal()`

## 實際應用

```kotlin
// 幫 Task 加一個轉換函數
fun Task.toLocal() = LocalTask(
    id = id,
    title = title,
    description = description,
    isCompleted = isCompleted,
)

// 使用
val localTask = task.toLocal()
```
