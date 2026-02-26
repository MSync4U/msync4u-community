# 🛠️ MSync4U Debugging Guide / 除錯指引

To help us fix issues in the **MSync4U** sync engine, we often need "Console Logs" from the background process. Please follow these steps to provide high-quality debug information.
為了協助修復 **MSync4U** 同步引擎的問題，我們通常需要背景程序的「主控台日誌 (Console Logs)」。請遵循以下步驟提供高品質的除錯資訊。

---

## 🚀 How to get Background Logs / 如何取得背景日誌

Since MSync4U is a browser extension, its core logic runs in the background. A standard `F12` on a webpage will **not** show these logs.
由於 MSync4U 是擴充功能，其核心邏輯在背景執行，一般網頁的 `F12` 看不到這些日誌。

### Step 1: Open Firefox Debugging
1. Open a new tab in Firefox.
2. Type `about:debugging#/runtime/this-firefox` in the address bar and press Enter.
3. 在網址列輸入 `about:debugging#/runtime/this-firefox` 並跳轉。

### Step 2: Inspect MSync4U
1. Find **MSync4U** in the list of extensions.
2. Click the **"Inspect" (檢查)** button. A new window will pop up.
3. 在擴充功能清單中找到 **MSync4U**，點擊 **「檢查」** 按鈕，這會彈出一個新視窗。

### Step 3: Capture the Console
1. In the new window, click the **"Console" (主控台)** tab.
2. Try to perform the action that caused the error (e.g., click "Sync Now").
3. Look for messages starting with **Error Codes** such as `E_SYNC_FAIL` or `E_TREE_CONFLICT`.
4. 在新視窗中切換到 **「Console」** 頁籤，重現錯誤操作，尋找以 **Error Code** 開頭的紅字訊息。

---

## ⚠️ Important: Privacy First / 重要：隱私叮嚀

**MSync4U** handles your "Bookmark Tree". When copying logs:
**MSync4U** 會處理您的「書籤樹」。複製日誌時請注意：

* **Redact Sensitive Data**: Please remove or mask any private URLs or bookmark titles before posting.
* **遮蔽敏感資料**：發布前請務必刪除或遮蔽私人的網址與書籤標題。
* **Only Error Codes Matter**: We primarily need the Error Code and the logic flow leading to the crash.
* **錯誤代碼最重要**：我們主要需要的是錯誤代碼以及導致崩潰的邏輯流程。

---

## 📋 Example of a Good Log / 良好日誌範例

```text
[M4-Sync] Start syncing profile: "Default"
[M4-Sync] Analyzing Bookmark Tree...
[M4-Error] E_SYNC_FAIL: Conflict detected at folder "Work/Project_A"
[M4-Error] Details: Remote version is newer than Local.
```
---
### 💬 Where to Send? / 傳送到哪裡？

Once you have the logs, please:
取得日誌後，請：

* **Open a [New Issue](https://github.com/MSync4U/msync4u-community/issues/new/choose)**.
* **Paste the logs** into the **"Console Logs"** section of our template.
* **建立一個 [新 Issue]**，並將日誌貼入模板的對應區塊中。

Thank you for helping us make **MSync4U** better!
感謝您協助我們讓 **MSync4U** 變得更好！
