
# 2016/1/4
中間テストの解説  
 
## 問1
### あ
```
cos(10t)u(t)
```
周期的である  
   
### い
```
X[n]=cos(10n)
```
x[0]=1この時のみ信号値なので周期的ではない

## 問2
### 信号がcausal
時間が０の時信号値は0
### システムがcausal
未来の値に依存しないシステム

16pに書いてある
```
x[n] = if n = -10: -1 else: 0
```
  
```
y[n] = if n = -2: -2 else: 0
```

#### 信号がcausalかどうか
n=-2のとき値が出てくるのでcausalではない  
  
#### システムがcausalかどうか
過去の入力のみを利用しているのでcausal  

## 問3
```
q[n]=x[n]-2q[n-1]
y[n]=q[n]+q[n-1]
```
方程式を解く
y[n]+2y[n-1]=

## 問4  
## 問5  
積分記号があるので連続。  
微分方程式を解く。上と解法がほぼ同じ  

## 問6
```
h[n] = if n = 1,2: 2 else: 0
x[n] = if n = -2,1: 2 else: 0
```
δの式に直す
```
h[n]=2δ[n-1]+2δ[n-2]
x[n]=2δ[n+2]+2δ[n+1]
```
入力```δ[n]```,出力```2δ[n-1]+2δ[n-2]```  
LTIシステムなので  
入力```2δ[n]```,出力```4δ[n-1]+4δ[n-2]```  
入力```2δ[n+2]```,出力```4δ[n+1]+4δ[n]```  
  
入力```2δ[n+1]```,出力```4δ[n]+4δ[n-1]```  
    
```
y[n]=PI{ 2δ[n+2]+2δ[n+1] }
    =4δ[n+1]+4δ[n]+4δ[n]+4δ[n-1]
    =4δ[n+1]+8δ[n]+4δ[n-1]
y[n]={4,8,4}
```
  
## 問7
### (1)一般的な方法
負の時はtが0なので,正の時はtを元に値が出る。   
立式してやるだけ  
```
y(t) = integral -INF to INF e^t dt
```

### (2)ラプラス変換を使った方法
```
Y(s)=H(s)X(s)
```
H(s)、X(s)それぞれのラプラス変換をして出し、  
積を部分分数分解して逆ラプラスをだす  
最後に```u(t)```をつける  
    
## 問8
  
**x(t-t<sub>0</sub>) <--> e<sup>-st<sub>0</sub></sup>X(s)**
  
h(t)=e<sup>-(t-1)</sup>u(t-1)  
H(s) = L[h(t)] = e<sup>-s</sup>1/(s+1)  
  
x(t)=e<sup>-3t</sup>u(t)  
X(s) = L[x(t)] = 1/(s+3)  
  
```
Y(s)=H(s)X(s)  
```

## 問9
ラプラス変換の定義に基づき解くだけ
  
X(z)= Sigma n = -INF to INF X[n]z<sup>-n</sup>  
z:複素変数  
z:遅れ演算子(Delay Operator)
z:進み演算子(Advance Operator)  

**Generallyと言う副詞はそうでない時もある事を強調している**
 
### Ex4.1 
X[n]= a<sup>n</sup>u[n]

X(z)  
=**Sigma k = -INF to INF a<sup>k</sup>u[k]z<sup>k</sup>**   
=**Sigma k = 0 to INF a<sup>k</sup>z<sup>k</sup>**  
=**Lim n->INF (1-(a/z)<sup>n+1</sup>)/(1-a/z)**

a!=z)
    1/(1-a/z) = z/(z-a)
ここで```|a|<=|z|```の場合収束しない    
  
### Ex4.2  
X[n]= a<sup>n</sup>u[-n-1]

X(z)  
=**Sigma k = -INF to INF a<sup>k</sup>u[-k-1]z<sup>k</sup>**   
=**- Sigma k = 1 to INF a<sup>k</sup>z<sup>k</sup>**  
=**1 - Sigma k = 0 to INF a<sup>k</sup>z<sup>k</sup>**  

=**1 - Lim n->INF (1-(a<sub>-1</sub>/z)<sup>n+1</sup>)/(1-a/z)**


**-u[-n-1]のZ変換は使わない**
