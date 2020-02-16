# conditional_gan_torch_mnist
mnistを学習するconditional GAN. pytorchを用いている.  

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

