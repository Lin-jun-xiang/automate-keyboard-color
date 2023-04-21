<div>
    <img src="https://readme-typing-svg.demolab.com/?pause=1&size=50&color=e065b3&center=True&width=1200&height=120&vCenter=True&lines=點選+⭐+Star+給予+開發者+支持;任何問題+皆可於+Issue+討論!" />
</div>

## 自動化鍵盤背光設定

* 需求
    * `Python`
    * 鍵盤驅動軟體

---

### 檔案說明及結構

* `color_grid_data.txt`: 紀錄您的鍵盤的每一個 RGB

* `keyboard_pos_data.txt`: 紀錄驅動軟體的 "鍵" 座標位置，視顯示器大小、驅動軟體改變，因此該資料一開始需要自己手動錄製

* `rgb_pos_data.txt`: 紀錄驅動軟體的 "RGB設定" 座標位置，視顯示器大小、驅動軟體改變，因此該資料一開始需要自己手動錄製

* `automator.py`: 負責有關 **"自動化"** 的程序

* `parse_image_color.py`: 負責解析圖片 RGB 的程序

* `config.py`: 設置檔案，包含 **"錄製相關快捷鍵"、"輸入圖片檔"、"控制介面"**...等
* `main.py`: 主要執行程式


```
.
├─ image/
│
├─ data
│  ├─ color_grid_data.txt
│  ├─ keyboard_pos_data.txt
|  ├─ rgb_pos_data.txt
|
├─ main.py
|
├─ config.py
|
├─ automator.py
|
├─ parse_image_color.py

```

---

### 重要提醒

* **鼠標快速移到螢幕左上角，可強制終止程序執行**

---

### 功能
* 將圖片檔案離散成 RGB 像素
* 將像素自動化設定至鍵盤背光
* 自動清除鍵盤背光 (初始化)

---

### 方法

```python
# 確認驅動軟體視窗名稱
def get_all_windows() -> None:
    import pyautogui

    windows = pyautogui.getAllWindows()
    for window in windows:
        print(f'{window.title}')
```


---

### 鼠標追蹤測試
```python
import pyautogui

pyautogui.displayMousePosition()
```

---

### 範例 (新盟x75)

##### 自動化設定 RGB

輸入 `image.png/jpg`，將 RGB 解析並設定在驅動軟體上

   ![RGB_setup](https://github.com/Lin-jun-xiang/automate-keyboard-color/blob/main/demo_video/automator_setup.gif?raw=true)

##### 自動化清除 RGB (初始化)

   ![RGB_cleanup](https://github.com/Lin-jun-xiang/automate-keyboard-color/blob/main/demo_video/automator_cleanup.gif?raw=true)



