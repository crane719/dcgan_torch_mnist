# dcgan_torch_mnist
mnistを学習するDCGAN. pytorchを用いている.  

## usage
### training
1. pythonのinstall  
2. packageのinstall  
```
pip install -r requirements.txt
```
3. training  
```
python train.py
```
4. 結果の確認  
学習終了後, ディレクトリ内にresultフォルダが作成されているため確認

### attention
mnistが存在しない場合, downloadを行うため, ネット環境が必要  

## abstract
### GAN
GAN(Generative Adversarial network)は生成モデルと識別モデルから成る.  
- Disctiminator(識別モデル)  
入力されるサンプルが生成モデルの分布から来たものか, 実際のデータ分布から来たものかを識別できるように学習する.  
- Generator(生成モデル)  
識別モデルに贋作と見破られないサンプルを生成するように学習を行う. 乱数からサンプルを生成する.  

### DCGAN
畳み込みを用いたGAN.  
高解像度化を行うCNNであえるLAPGANより発想を得ている. 以下のような特徴  
- poolingを用いず, 畳込みのみで次元削減  
- generator, discriminatorともにbatchnorm  
- 全結合層の削除  
- generatorの活性化関数は最終出力がtanh, それ以外はrelu  
- discriminatorはすべてleaky relu  
- zは一様乱数  

## 学習過程
- 1epoch  
![2](https://user-images.githubusercontent.com/54930418/74597680-7242e000-50a6-11ea-8278-945fc554e6be.png)

- 25epoch  
![25](https://user-images.githubusercontent.com/54930418/74597682-7f5fcf00-50a6-11ea-87b8-8e22f7afbd0b.png)

- 100epoch  
![100](https://user-images.githubusercontent.com/54930418/74597687-8555b000-50a6-11ea-89ec-2a954b81d7ea.png)

- gif  
![index2](https://user-images.githubusercontent.com/54930418/74597719-19c01280-50a7-11ea-86d6-8e729e8f970c.gif)


