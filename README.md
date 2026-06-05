# 簡單線性迴歸圖表產生器

這是一個使用 Streamlit 製作的互動式網頁工具，可以隨機產生簡單線性迴歸資料，使用 `scikit-learn` 建立線性迴歸模型，並在圖表中標示出殘差最大的離群值。

產生資料的公式如下：

```text
y = aX + b + noise
```

程式會自動產生真實斜率 `a`、截距 `b`、雜訊變異數，接著用線性迴歸模型估計最佳斜率與截距，最後計算每筆資料的 residual 與 abs_residual。

## Demo 網站

本專案可以用 Streamlit 啟動成網頁版 Demo。

啟動後請開啟：

```text
http://localhost:8501
```

啟動指令：

```powershell
streamlit run linear_regression_plot_generator.py
```

如果之後部署到 Streamlit Community Cloud，可以將公開網址放在這裡：

```text
https://your-streamlit-demo-url.streamlit.app
```

## 功能特色

- 隨機產生 `X` 與 `Y` 資料
- 隨機產生真實斜率 `a`
- 隨機產生真實截距 `b`
- 隨機產生雜訊變異數 variance
- 使用 `LinearRegression` 建立線性迴歸模型
- 顯示真實參數與模型估計參數
- 計算 `residual` 與 `abs_residual`
- 找出 Top K 離群值
- 繪製資料點、迴歸線、離群值
- 使用 Streamlit 提供互動式參數調整

## 專案檔案

```text
.
+-- linear_regression_plot_generator.py
+-- requirements.txt
+-- linear_regression_data.csv
+-- linear_regression_plot.png
+-- README.md
```

## 安裝套件

請在專案資料夾中執行：

```powershell
pip install -r requirements.txt
```

## 啟動方式

使用 Streamlit 啟動網頁：

```powershell
streamlit run linear_regression_plot_generator.py
```

啟動成功後，終端機會顯示本機網址，例如：

```text
http://localhost:8501
```

將網址貼到瀏覽器即可使用。

## 可調整參數

側邊欄可以調整以下參數：

- `n`：資料筆數
- `x_min`、`x_max`：X 值範圍
- `a_min`、`a_max`：真實斜率範圍
- `b_min`、`b_max`：真實截距範圍
- variance range：雜訊變異數範圍
- random seed：隨機種子
- Top K Outliers：要標示的離群值數量

## 輸出資料欄位

完整資料表包含以下欄位：

```text
X
Y
Y_pred
residual
abs_residual
is_outlier
```

Top K 離群值表格包含以下欄位：

```text
X
Y
Y_pred
residual
abs_residual
```

## 主要函式

- `generate_data()`：產生隨機線性資料
- `fit_linear_regression()`：建立並訓練線性迴歸模型
- `find_top_outliers()`：依照絕對殘差找出離群值
- `plot_regression()`：繪製迴歸圖表
- `main()`：啟動 Streamlit 網頁介面

## 使用技術

- Python
- NumPy
- Pandas
- Matplotlib
- scikit-learn
- Streamlit

## 備註

本專案使用 matplotlib 的 `Agg` backend，讓圖表在沒有 GUI backend 的環境中也能正常產生。
