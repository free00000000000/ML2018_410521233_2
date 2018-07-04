# ML2018_410521233_2

### 1. Downloading Dataset
MNIST 的資料由 tensorflow.examples.tutorials.mnist 下載

Dataset 內包含：
- train: 55000 筆
- test: 10000 筆
- validation: 5000 筆

### 2. Preprocessing Character Images
- 去掉空白的部份

### 3. Reducing Dimension

1. Principal Component Analysis (PCA)
    - 這次採用 sklearn 內建的 PCA 模型。
    - PCA 為非監督式學習，最大的問題在於我們不知道 k，也就是說不知道要降到 k 維度時是否合適。由於 PCA 的實做過程會丟失一些參數，運用樣本與樣本間的投影均方誤差，讓這個誤差介於0.95到0.97之間，可以有效降維，也可以使降維後的資料不至於失真


2. Linear Discriminant Analysis (LDA)

### 4. Choosing a Classifier and Training It

1. Logistic regression
    - 沒去掉空白 ＆ 沒做 pca --> accuracy: 0.9198, time: 62.6s
    - 去掉空白 ＆ 沒做 pca --> accuracy: 0.9316, time: 278.1s
    - 沒去掉空白 ＆ 做 pca --> accuracy: 0.9146, time: 29.4s
    - 去掉空白 ＆ 做 pca --> accuracy: 0.9297, time: 29.7s

2. Convolutional neural network (CNN)
    - 輸入圖片有去掉空白部份
    - label 用 onehot encoding 表示
    - Accuracy: 0.9766


### 5. Evaluating the Performance
- 在測試 Logistic regression 時發現到，相同條件下，pca 在降維的同時會降低準確率，但在速度上能得到很大的提升，大幅的增加效率。而去掉邊緣空白處，會使得準確率提升一點，因為只有 2% 左右效果不算顯著。
- 測試 CNN 發現到，CNN 在辨識影像的部份比起邏輯回歸這樣的線性模型有更好的效果。


