# Kotlin Function Reference

## 是什麼

用 `::` 把函數本身當作參數傳遞，而不是直接呼叫它。

## 語法

```kotlin
類別::函數名稱
```

## 範例

```kotlin
// 一般呼叫（執行函數）
task.toLocal()

// 函數引用（把函數當參數）
Task::toLocal
```

## 搭配 map() 使用

```kotlin
// 完整寫法
fun List<Task>.toLocal() = map { task -> task.toLocal() }

// 簡潔寫法（用函數引用）
fun List<Task>.toLocal() = map(Task::toLocal)
```

兩種寫法結果完全一樣。

## map() 是什麼

對 List 裡的每一個元素執行某個函數，回傳新的 List。

```kotlin
listOf(1, 2, 3).map { it * 2 }  // 回傳 [2, 4, 6]
```

## 重點

- `::` = 引用函數本身，不是呼叫它
- 搭配 `map()`、`filter()` 等高階函數使用時，可以讓程式碼更簡潔
