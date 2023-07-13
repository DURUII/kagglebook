## 範例程式

「Kaggle 競賽攻頂秘笈 - 揭開 Grandmaster 的特徵工程心法，掌握制勝的關鍵技術」([amazon](https://www.amazon.co.jp/dp/4297108437)、[旗標](https://www.flag.com.tw/books/product/F1365)) 範例程式。


### 每個資料夾的內容

|資料夾 | 内容 |
|:----|:-------|
| input | 資料集 |
| ch01 | 第1章範例程式 |
| ch02 | 第2章範例程式 |
| ch03 | 第3章範例程式 |
| ch04 | 第4章範例程式 |
| ch05 | 第5章範例程式 |
| ch06 | 第6章範例程式 |
| ch07 | 第7章範例程式 |
| ch04-model-interface | 第4章「用於競賽的 Class 和專案目錄結構」範例程式 |

* 以每章的目錄為工作目錄執行程式
* 請以[input/readme.md](../../Downloads/F1365_sample_code%202/input/readme.md) 說明下載程式
* 第4章「用於競賽的 Class 和專案目錄結構」範例程式，請山考[ch04-model-interface/readme.md](../../Downloads/F1365_sample_code%202/ch04-model-interface) 


### Requirements

範例程式已經在 Google Cloud Platform (GCP) 驗證過

環境如下

* Ubuntu 18.04 LTS  
* Anaconda 2019.03 Python 3.7
* 必要的 Python 套件

使用以下方式建立 GCP 環境
```
# utils -----

# 安裝開方工具
cd ~/
sudo apt-get update
sudo apt-get install -y git build-essential libatlas-base-dev
sudo apt-get install -y python3-dev

# anaconda -----

# 下載安裝 Anaconda
mkdir lib
wget --quiet https://repo.continuum.io/archive/Anaconda3-2019.03-Linux-x86_64.sh -O lib/anaconda.sh
/bin/bash lib/anaconda.sh -b

# 設定 PATH
echo export PATH=~/anaconda3/bin:$PATH >> ~/.bashrc
source ~/.bashrc

# python packages -----

# 安裝 Python 套件
# numpy, scipy, pandas 還是 Anaconda 2019.03 的版本
# pip install numpy==1.16.2 
# pip install scipy==1.2.1 
# pip install pandas==0.24.2
pip install scikit-learn==0.21.2

pip install xgboost==0.81
pip install lightgbm==2.2.2
pip install tensorflow==1.14.0
pip install keras==2.2.4
pip install hyperopt==0.1.1
pip install bhtsne==0.1.9
pip install rgf_python==3.4.0
pip install umap-learn==0.3.9

# set backend for matplotlib to Agg -----

# 指定 matplotlib 後端在 GCP 上面執行
matplotlibrc_path=$(python -c "import site, os, fileinput; packages_dir = site.getsitepackages()[0]; print(os.path.join(packages_dir, 'matplotlib', 'mpl-data', 'matplotlibrc'))") && \
sed -i 's/^backend      : qt5agg/backend      : agg/' $matplotlibrc_path
```
