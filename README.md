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


### 5. Evaluating the Performance
- 在測試 Logistic regression 時發現到，pca 在降維的同時會降低準確率，但在速度上能得到很大的提升，大幅的增加效率。
- 測試 CNN 發現到，CNN 在辨識影像的部份比起像邏輯回歸這樣的線性模型有更好的效果。


