# Git 踩坑紀錄

## 問題：push 被拒絕，沒有權限

### 錯誤訊息
```
ERROR: Permission to android/architecture-samples.git denied to Martykk.
fatal: Could not read from remote repository.
```

### 原因
`git clone` 別人的專案後，`origin` 預設指向原始 repo（這裡是 Google 的）。
直接 `git push` 會試圖推到 Google 的 repo，但你沒有寫入權限。

### 解法
先在 GitHub 建立自己的 repo，再把 `origin` 換成自己的網址：

```powershell
git remote set-url origin https://github.com/你的帳號/你的repo名稱.git
git push -u origin main
```
