---
title: 事業価値とキャッシュ・フロー
layout: default
parent: Investment Science
nav_order: 1
---

# 事業価値とキャッシュ・フロー

## ストックとフロー
ビジネス・プロジェクト（事業）の財務的価値（**事業価値**）は，その事業から発生する**キャッシュ・フロー流列**(CSF: *cash flow streams*)によって決定される．

ここで，事業価値というのは**ストック**の概念であるのに対し，キャッシュ・フローとは文字通り**フロー**の概念である．風呂水を例にすれば，バスタブに溜っている水の量[L]がストックであり，1分あたりにバスタブに流れ込む（あるいは流れ出す）量[L/s]がフローである．風呂水の場合，ストックとフローの関係は，以下の式で表される：
$$
\begin{equation}
S = \sum_{s=0}^{T} f(s) \Delta t
\label{eq:bathtub}
\end{equation}
$$
ここで，$S$は時点$T$の期末における風呂水の量（ストック），$f(s)$は時点$s=0,1,2,\cdots,T$の期初から期末までに流れ込む水の単位時間あたりの量（フロー），$\Delta t$は単位時間で計った1時点の長さである．ここで，$f(s) \Delta t$ は，フロー[L/s]と時間長[s]の積であるから，時点$s$の期初から期末までに流れ込む水の量（ストック）を表していることに注意されたい．

{: .note}
> 上記のような離散的な**時点** と **時刻** の関係を考える場合は，「期初」と「期末」の2つの **時刻** の違いに留意する必要がある．現在時刻を$\tau=0$とし，10分後までの1分ごとの**時刻**$\tau = 1, 2, \cdots, 10$を考えよう．$\tau=1,2,\cdots,10$の各時刻を「期末」とする離散時点$s=0,\cdots,9$を考えたとき，それぞれの時点の期初と期末の時刻は次のように整理できる．
> 
> | 時点 | 期初の時刻 | 期末の時刻 |
> |:---|:---|:---|
> | $s=0$ | $\tau = 0$ | $\tau = 1$|
> | $s=1$ | $\tau = 1$ | $\tau = 2$|
> | $\vdots$ | $\vdots$ | $\vdots$ |
> | $s=9$| $\tau = 9$ | $\tau = 10$ |
> 
> この離散時点の下で，$s=9$の期末（$\tau=10$）までに毎秒20mLの水が流れ込むとする．このとき，単位時間[秒]で計った時点の長さは$\Delta t = 60$であり，フローは$f(s)=20$ [mL/s] であるから，時点$s=9$の期末までに流れ込む水の総量は以下の式で表される： 
> $$\begin{equation}
> \sum_{s=0}^{9} f(s) \Delta t = \sum_{s=0}^{9} (20 \times 60) = 12,000 \text{[mL]}
> \end{equation}$$

このような風呂水の場合は式\eqref{eq:bathtub}で良いが，キャッシュ・フローを評価するためには**割引**による**現在価値**への換算が必要である．

## 利子/割引と現在価値
ある事業から1000万円の収益が発生するとして，その収益が今年得られるのと20年後に得られるのでは，明らかに後者の方が価値が低い．将来発生するキャッシュ・フローを現在の価値に換算したものを**現在価値** (present value)と呼ぶ．現在価値への変換方法で最も簡単なのは，**利子率** (interest rate)を用いる方法だ．

いま銀行に$X$円預け，年利$R$で1年間運用した場合，来年受取ることのできる金額は$(1+R)X$円である．つまり，今年得られる$X$円と来年得られる$(1+R)X$円は同じ価値を持つ．換言すれば，来年得られる$X$円の現在価値は
$$\begin{equation}
\frac{1}{1+R} X
\end{equation}$$
で表される．いちいち分数で書くのは面倒なので，1年間の**割引係数**を
$$
\begin{equation}
\beta = \frac{1}{1+R}
\end{equation}
$$
と定義し，$\beta X$と書くことにする．

年利$R=0.01$の場合，割引係数は$\beta = 1/1.01 \approx 0.9901$である．従って，来年得られる1000万円の現在価値は，$1000/1.01\approx 990.1$万円と求められる．

2年後に得られる収益の現在価値はどうなるだろうか．いま銀行に$X$円預け，年利$R$で1年運用した場合，1年後には$(1+R)X$円になる．これを再び銀行に預けてもう1年運用すれば，2年後には$(1+R)^{2}X$円になる．このように「金利が生み出す金利」のことを **複利** (compound interest)と呼ぶ．
複利計算の下では，今年の$X$円と2年後の$(1+R)^{2}X$円は同じ価値を持つ．このことは，2年後に得られる$X$円の現在価値が
$$
\begin{equation}
\left(\frac{1}{1+R}\right)^{2}X = \beta^{2} X
\end{equation}
$$
で表されることを意味している．同様に考えれば，任意の$s \geq 1$について，$s$年後に得られる$X$円の現在価値は，以下で表される：
$$\begin{equation}
\beta^{s} X
\end{equation}$$

ここまでの準備に基づいて，ある事業から発生するキャッシュ・フロー流列の現在価値を定義しよう．
ある事業において，毎年の$s=0, 1, 2, \cdots, T$のキャッシュ・フロー流列$\{F(s): s = 0, 1, \cdots, T\}$が与えられたとしよう．ここで，$F(s)$は，時点$t$の期初から期末までに発生する年間キャッシュフローである．このとき，キャッシュ・フロー流列の現在価値は，以下の式で表される：
$$
\begin{align}
S(s) &= \sum_{s=0}^{T} \beta^{s} F(s) \\
&= F(0) + \beta F(1) + \beta^{2} F(2) + \cdots + \beta^{T} F(T)
\label{eq:discounted_annual_cash_flow}
\end{align}
$$

### 練習問題
{: .warning}
> あとで考える

## 時点の長さと連続複利
風呂水の式\eqref{eq:bathtub}と
式


# 現在正味価値と投資意思決定
設備投資や研究開発投資といった**投資**は，「資産を投じる」ことによって将来のキャッシュ・フローの変化・発生を目論むものである．合理的な投資意思決定のためには，投じる資産（ストック）に対して，発生するキャッシュ・フローが見合うものか否かを評価する必要がある．

いま，時点$s=0$に$C$だけの投資を行うことで，以降の時点$s=0,1,\cdots, T$にキャッシュ・フロー流列$\{f(s): s = 0, 1, \cdots, T\}$を発生する事業を考えよう．<span style="color:red; font-weight:bold;">ただし，以下では，1時点の長さは（利子の単位と同じ）1年間とする</span>この事業に投じる資金（ストック）は$C$であり，その見返りとして獲得できるキャッシュ・フローの現在価値（ストック）は$\sum_{s=0}^{T} \beta^{s} f(s) \Delta t$である．このとき，事業の収入と支出の差：
$$\begin{equation}
\sum_{s=0}^{T} \beta^{s} f(s) \Delta t - C
\end{equation}$$
を現在正味価値(NPV: *net present value*)と呼び，これが正であるならば，その投資は正当化される．

プロジェクトによっては，実際のキャッシュ・フローを得るまでに段階的な投資が必要だったり，投資のタイミングとキャッシュ・フローが発生し始めるタイミングが一致しないものもある．例えば，新薬開発事業は，通常，承認されるまでに何段階もの治験研究が必要であり，承認から製造・販売までにもラグが生じる．上述した現在正味価値を用いた方法は，そうした場合にも汎用的に適用できる．

例えば，2つの時点$s=0$および$s=5$において，それぞれ，$C_{0}$および$C_{1}$だけの投資を行うことで，時点$s=10$の期初から$s=19$の期末にわたり$\{f(s): t = 10, 11, \cdots, 19\}$だけのキャッシュ・フロー流列が発生する事業を考える．この事業の収入と支出の発生時点と$s=0$の期初における現在価値は，それぞれ，以下の表のように整理できる：

|項目|発生時点|金額（負の場合は支出）|現在価値|
|:---|:---|:---|:---|
|1段階目の投資|$s=0$|$-C_{0}$|$-C_{0}$|
|2段階目の投資|$s=5$|$-C_{1}$|$-\beta^{5}C_{0}$|
|キャッシュフロー|$s=10,11,\cdots,19$|$f(s) \Delta t$|$\beta^{t} f(s)\Delta t$|

これより，この事業の現在正味価値は
$$\begin{equation}
V(0) = -C_{0} - \beta^{5} C_{1} + \sum_{s=10}^{19} \beta^{s} f(s) \Delta t
\end{equation}$$
と表される．

### 練習問題
{: .warning}
あとで考える

# 
# 将来時点での現在正味価値と漸化式
## 将来時点での現在正味価値
上述した投資事業の，将来時点$t > 0$で評価した現在正味価値（将来時点を「現在」と呼ぶことに違和感があるなら「当時価値」と読み替えてよい）を考えてみよう．例えば，$t=1$の場合，初期時点での投資$C_{0}$は既に実行済であるから，残る投資は時点$s=5$における$C_{1}$のみである．この投資の時点$t=1$での価値は，額面$C_{1}$を$s-t=4$期分だけ割引いた
$$\begin{equation}
\beta^{(s-t)} C_{1} = \beta^{(5-1)}C_{1}
\end{equation}$$ 
で表される．同様に，$s=10$以降で発生するキャッシュフローの$s=1$での現在価値は，
$$\begin{equation}
\sum_{s=10}^{19} \beta^{(s-1)} f(s) \Delta t
\end{equation}$$
で表されるから，当該事業の$t=1$での事業価値は
$$\begin{equation}
V(1) = - C_{1}^{(5-1)} + \sum_{s=10}^{19} \beta^{(s-1)} f(s) \Delta t
\end{equation}$$
と表される．同じことが$t=2,3,4,5$についても成り立つから，時点$t=1, \cdots, 5$における事業価値は
$$\begin{equation}
V(t) = - C_{1}^{(5-t)} + \sum_{s=10}^{19} \beta^{(s-t)} f(s) \Delta t, \qquad s = 1, \cdots, 5
\end{equation}$$
と書ける．

次に，$t=6$での事業価値を考えてみよう．この時点では，2段階目の投資も実行済のため，当該事業の価値は，時点$s=10$以降に発生するキャッシュ・フローのみとなる．各時点で発生するキャッシュ・フローの時点$t=6$での価値の和（i.e. $t=6$における事業価値）は，以下の式で表される：
$$\begin{equation}
V(6) = \sum_{s=10}^{19} \beta^{(s-6)} f(s) \Delta t
\end{equation}$$
同じことが$t=7, 8, 9, 10$についても成り立つから，時点$t=6, \cdots, 10$における事業価値は
$$\begin{equation}
V(t) = \sum_{s=10}^{19} \beta^{(s-t)} f(s) \Delta t, \qquad t = 6, \cdots, 10
\end{equation}$$
と書ける．

さらに，$t=11$での事業価値を考えてみよう．この時点では，最初のキャッシュ・フロー$f(10)$は既に発生し終わっているため，この時点での事業価値は，残期間中に発生するキャッシュ・フローの$t=11$での価値の総和に等しい：
$$\begin{equation}
V(11) = \sum_{s=11}^{19} \beta^{(s-11)} f(s) \Delta t
\end{equation}$$
同じことが$t=12, \cdots, 19$についても成り立つため，時点$t=11, \cdots, 10$における事業価値は，
$$\begin{equation}
V(t) = \sum_{s=t}^{19} \beta^{(s-t)} f(s) \Delta t, \qquad s = 11, \cdots, 19
\end{equation}$$
と書ける．

従って，この事業の時点$t=0, 1, \cdots, 19$における価値は，以下のように整理できる：
$$\begin{equation}
V(t) = 
\begin{cases}
-C_{0} - \beta^{5} C_{1} + \sum_{s=10}^{19} \beta^{s} f(s) \Delta t & t = 0\\
-\beta^{(5-t)} C_{1}  + \sum_{s=10}^{19} \beta^{(s-t)} f(s) \Delta t & t = 1, \cdots, 5\\
\sum_{s=10}^{19} \beta^{(s-t)} f(s) \Delta t & t = 6, \cdots, 10\\
\sum_{s=t}^{19} \beta^{(s-t)} f(s) \Delta t & t = 11, \cdots, 19\\
\end{cases}
\end{equation}$$

## 現在正味価値が従う漸化式
プロジェクト価値$\{V(t): t = 0, 1, \cdots, 19\}$について，$V(t)$と$V(t+1)$の間に成立する漸化式を導こう．まず，$V(18)$と$V(19)$は
$$
\begin{align}
V(18) &= f(18) \Delta t + \beta f(19) \Delta t\\
V(19) &= f(19) \Delta t
\end{align}
$$
であるから，以下の漸化式が成立する：
$$
V(18) = f(18) \Delta t + \beta V(19)
$$
同様に，$V(17)$と$V(18)$は
$$
\begin{align}
V(17) &= f(17) \Delta t + \beta f(18) \Delta t + \beta^{2} f(19) \Delta t\\
&= f(17) \Delta t + \beta \left\{f(18) \Delta t + \beta f(19) \Delta t\right\}\\
V(18) &= f(18) \Delta t + \beta f(19) \Delta t
\end{align}
$$
であるから，やはり以下の漸化式が成り立つ：
$$\begin{equation}
V(17) = f(17) \Delta t + \beta V(18)
\end{equation}$$
実際，$t=19 \sim 11$までは，
$$\begin{align}
V(t) &= f(t) \Delta t + \sum_{s=t+1}^{19} \beta^{(s-t)}f(s) \Delta t\\
&= f(t) \Delta t + \beta \left( 
    \sum_{s=t+1}^{19} \beta^{(s-(t+1))} f(s) \Delta t 
    \right)\\
V(t+1) &=  \sum_{s=t+1}^{19} \beta^{(s-(t+1))} f(s) \Delta t
\end{align}$$
であるから，$V(t)$と$V(t+1)$の間に以下の漸化式が成立する：
$$\begin{equation}
V(t) = f(t) \Delta t + \beta V(t+1), \quad t = 11, \cdots, 18
\end{equation}$$

キャッシュ・フローが発生しない時点$t=9$については，
$$\begin{align}
V(9) &= \sum_{s=10}^{19} \beta^{(s-9)} f(s) \Delta t\\
&= \beta \left( \sum_{s=10}^{19} \beta^{(s-10)} f(s) \Delta t \right)\\
V(10) &= \sum_{s=10}^{19} \beta^{(s-10)} f(s) \Delta t
\end{align}$$
より，以下の漸化式が成り立つ：
$$\begin{equation}
V(9) = \beta V(10)
\end{equation}$$
$t=8 \sim 6$および$t=4 \sim 1$についても，同様に，
$$\begin{align}
V(t) &= \sum_{s=10}^{19} \beta^{(s-t)} f(s) \Delta t\\
&= \beta \left( \sum_{s=10}^{19} \beta^{(s-(t+1)} f(s) \Delta t \right)
V(t+1) &= \sum_{s=10}^{19} \beta^{(s-(t+1))} f(s) \Delta t
\end{align}$$
より$V(t)$の漸化式が得られる：
$$\begin{equation}
V(t) = \beta V(t+1), \qquad t = 1,\cdots,4, 6, \cdots, 8
\end{equation}$$


最後に，投資費用が発生する$t=5$についても漸化式を導いておこう．
$$\begin{align}
V(5) &= -C_{1} + \sum_{s=10}^{19} \beta^{(s-5)} f(s) \Delta t\\
&= -C_{1} + \beta \left( \sum_{s=10}^{19} \beta^{(s-6)} f(s) \Delta t \right)\\
V(6) &= \sum_{s=10}^{19} \beta^{(s-6)} f(s) \Delta t
\end{align}$$
より
$$\begin{equation}
V(5) = -C_{1} + \beta V(6)
\end{equation}$$
と書ける．同様に，$V(0)$と$V(1)$の間にも以下の関係が成り立つ：
$$\begin{equation}
V(0) = -C_{0} + \beta V(1)
\end{equation}$$

結局のところ，$V(t)$が従う漸化式とその終端条件は，以下のように整理される：
$$
\begin{align}
V(t) &= \begin{cases}
f(t) \Delta t + \beta V(t+1) & t=10, \cdots, 18\\
\beta V(t+1) & t = 1, \cdots, 4, 6, \cdots, 9\\
-C_{1} + \beta V(t+1) & t=5\\
-C_{t} + \beta V(t+1) & t=0
\end{cases} \label{eq:recurrence_V}\\
V(19) &= f(19) \Delta t
\end{align}
$$

この漸化式を活用すると，以下のシンプルな手手続きで全ての時点の価値$\{V(t): t = 0, 1, \cdots, 19\}$を求められる．
- Step 0: $V(19): = f(19) \Delta t$ とし，$t=18$とする．
- Step 1: 式\eqref{eq:recurrence_V}を用いて，既知の$V(t+1)$から$V(t)$を計算する．
- Step 2: $t=0$なら終了．そうでなければ，$t:=t-1$として Step 1 に戻る．

# 練習問題
{: .warining}
> あとで考える