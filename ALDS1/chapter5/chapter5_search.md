## 第５章 探索
### 線形探索
配列の先頭から各様ヨガ目的の値と等しいか順番に調べる愚直で確実な方法。効率は悪いがデータの並び方に関係なく適用できる。

### 二分探索
コンピュータのデータはすでにある項目によって整列され管理されている場合が多い。そのような場合は効率的な探索アルゴリズムを適用することができる。二分探索はデータの大小を利用した探索アルゴリズムである。

キーの昇順に並んだデータが配列に格納されているとする。  
* 1.配列全体を探索範囲とする。  
* 2.探索の範囲内の中央の要素を調査。  
* 3.目的のキーと中央の要素のキーが一致すれば終了。  
* 4.目的のキーが中央の要素のキーより小さければ前半部分、大きければ後半部分を次の探索範囲として2に戻る。  

### Hash法
Hash法では、Hash関数と呼ばれる関数値によって、要素の格納場所を決定する。これはHashテーブルと呼ばれる表を用いたアルゴリズムである。要素のキーを引数とした関数を呼び出すだけでその位置を特定することができるのでデータの種類によっては高速なデータの探索が可能になる。

### イテレータ
コンテナの要素に対して反復処理を行うためのオブジェクト。
- "++" ... イテレータを次の要素に進める
- "==,!=" ... 2つのイテレータが同じ位置を示しているかどうかを返す
- "=" ... 左辺のイテレータが参照している要素の「位置」に右辺の値を代入する
- "*" ... そに位置にある要素を返す

どの種類のコンテナに対しても同じ文法でそれらの要素に順番にアクセスできるのが特徴。

コンテナはイテレータを扱うための同じ名前のメンバ関数を提供。begin(),end()などがその代表的関数である。

### lower_bound
ソート済みの範囲に対するアルゴリズム。指定した値以上の最初の要素の位置をイテレータで返す。これはソート状態を崩さずに指定した値を新たに挿入することができる最初の位置を示すのと同意です。（一方のupper_boundは指定した値より大きい最初の要素の位置を返す。）

lower_boundは最初の2つの引数で対象となる配列やコンテナの範囲を指定。
例えばprogram5-7に見られる、lower_bound(A, A+14, 3)は配列Aの先頭ポインタとそこから14離れた位置、つまり配列の末尾を指定している。(Aがvectorの場合はA.begin(),A.end()を使って指定することもできる。)3つ目の引数にはvalueをしてい。ここでは3となっているので3以上の最初の要素であるA[5]を指すポインタが*posに代入される。ちなみにdistanceは2つのポインタの距離を返す関数。