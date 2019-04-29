# DSAI_HW2
## Analyze the results
* RNN皆爲兩層的LSTM
### Training epoch (3 digits)
* add : 在第 36 epoch, val_acc 達到 90%, 在第 109 epoch, val_acc 達到最高 99%
  * ![](https://imgur.com/okX0NZB.png)
* sub : 在第 83 epoch, val_acc 達到 90%, 在第 137 epoch, val_acc 達到最高 96%
  * ![](https://imgur.com/rTIr7hp.png)
* combine : 在第 167 epoch, val_acc 達到最高 88%
  * ![](https://imgur.com/lqYTezh.png)
* test acc : 在 test 時候，我不是用 model 的 evaluation，而是當整個算式正確，才視為正確 (與訓練時的以每一位數去計算不同)
  * add : 0.9651
  * sub : 0.8976								
  * combine : 0.5943
* 減法比加法慢收斂，將加法和減法合在一起更慢收斂
* 當 val_acc 越高時 正確的算式率也會越高，但當 val_acc 較低時，正確的算式率會下降很快

### Different number of digits (add, 200 epoch)
* 3 digits : 在第 36 epoch, val_acc 達到 90%, 在第 109 epoch, val_acc 達到 99%
  * ![](https://imgur.com/okX0NZB.png)
* 5 digits : 在第 50 epoch, val_acc 達到 66%
  * ![](https://imgur.com/EZg2tc9.png)
* test acc : 
  * 3 digits : 96.51%
  * 5 digits : 10.28%
* 猜測是因為 train data 不足導致 5 digits 的時候收斂在正確率比較低的地方
  
### Training size (add, 200 epoch, 3 digits)
* training data 都是取全部資料的 1/4
* 全部共 80000 筆 :  在第 36 epoch, val_acc 達到 90%, 在第 109 epoch, val_acc 達到 99%
  * ![](https://imgur.com/okX0NZB.png)
* 全部共 40000 筆 : 在第 121 epoch, val_acc 達到 82%
  * ![](https://imgur.com/6fIMp3V.png)
* test acc : 
  * 80000 筆 : 96.51%
  * 40000 筆 : 47%
  
### Multiplication (200 epoch, 3 digit, training size:80000)
* 在第 88 epoch, val_acc 達到 58%
  * ![](https://imgur.com/Y9mADke.png)
* test acc : 1.3%
* test acc 這麼小是因為答案可能會到達六位數，而訓練的時候是以每一位為單位訓練的


  
  
