# yzuCourseBot 元智選課機器人

## Update log
- 2019/12/11 
	- [修改] 優化判斷是否登入成功的方式
	- [修改] 優化部分hard code的地方
	- [新增] 判斷使用者的課程ID是否存在 

## Introduction
最近在整理code丟上github，況且上學期還訓練了一個高辨識率的model(請參考 [CNN-model-for-YZU-cpatcha-OCR](https://github.com/Doem/CNN-model-for-YZU-cpatcha-OCR))，所以就順手將之前寫的選課機器人從pytesseract替換成自己訓練的CNN model，並移除selenium的依賴改純用requests的方式去模擬選課動作。由於改寫的時間不是很多並沒有寫得很好，歡迎各位提交Bug上來我會再找時間修正的。

## Dependencies
|Name|
|----|
|lxml|
|keras|
|numpy|
|opencv|
|requests|
|configparser|
|BeautifulSoup|

### For Ubuntu
```
apt-get install -y libsm6 libxext6 libxrender-dev
pip3 install opencv-python beautifulsoup4 keras tensorflow lxml
```

## Remind
請斟酌使用本機器人程式，並自行負責使用後所造成的損失!

## Usage

### 1. 新增 `accounts.ini` 存放Portal帳密的檔案，格式如下:
```
[Default]
Account= your account
Password= your password
```

### 2. 修改 `yzuCourseBot.py` 中的`coursesList`變數新增想選的課程清單，格式如下:
```
coursesList = [
    '304,CS352A', 
    '901,LS239A', 
    '304,CS354A'
]
```

**304**: 為系所編號

**CS352A**: 為課程編號加上班級編號，CS352 + A

以上資訊都能在課程查詢網站或是選課系統中得知的訊息

### 3. 執行 `yzuCourseBot.py`
```
$ python yzuCourseBot.py
```

**請用Python3以上的版本執行**


## Bug Report
請來信 aa0917954358@gmail.com 或是開issue，謝謝!