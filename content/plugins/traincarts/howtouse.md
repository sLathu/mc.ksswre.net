---
title: TrainCarts の使い方・コマンド
noToc: true
description: TrainCarts の使い方やコマンドを解説します
---

TrainCarts の使い方やコマンドを解説します。

## トロッコを連結させる
トロッコを複数台線路に置いてトロッコを衝突させると、衝突したトロッコ同士が自動的に連結します。

## コマンド
トロッコに乗った状態でコマンドを打つことで、そのトロッコに対してコマンドが実行できます。

TrainCarts は `/train` と `/cart` コマンドがあって、`/train` は連結したトロッコに対する操作、`/cart` は一つのトロッコに対する操作です。


### トロッコの情報を見る
```
/train info
/train i
```

### トロッコの所有者を自分にする
```
/train claim
/carts claim
```

### トロッコのスピード上限を変更する
デフォルトは 0.5 (blocks/tick) です。
あまりにも速くするとラグの影響を受けて描画が間に合わなくなったり、サーバに負荷がかかります。
変更した値はパワードレールによる加速にも適用されます。パワードレールを複数使うことで最高速度まで加速します。
```
/train maxspeed 1
```

### トロッコが衝突しても連結しないようにする
```
/train linking false
```

### 衝突を無視して走行しつづけるようにする
デフォルトは true
```
/train setcollide false
```

### トロッコに名前をつける
上はリモートコントロールなど、内部的に使用するときの名前です。看板に記述するので出来る限り短い名前の方がいいですが、ユニークである必要があります。
下は表示名です。看板と連携したときこちらの名前が表示されます。他のトロッコと名前が被っても大丈夫。
```
/train setname <name>
/train setdname <name>
```

### トロッコの近くにプレイヤーが居なくてもチャンクが読み込まれるようにする
これを有効化することでプレイヤーが居ない状態でもチャンクがアンロードされません。
つまり、トロッコが常に動くようになります。遠くに行ったきり帰ってこない、なんてことがなくなります。
その反面、サーバに負荷がかかります。
```
/train keepchunksloaded true
```

### トロッコを削除する
```
/train destroy  -- 連結したトロッコを全て削除
/carts destroy  -- 連結したトロッコのうち現在選択されたトロッコのみを削除
```

## 看板と連携して TrainCarts のトロッコの情報を表示する
SignLink (tskserver には導入済み) というプラグインを使うと、TrainCarts のトロッコの情報を看板に表示することができます。
TrainCarts の看板による [Trigger 機能](signs/trigger)を使用します。

## その他コマンド
コマンドについてより詳しく知りたい場合は [Wiki](https://minecraft.gamepedia.com/Custom_servers/Bukkit/TrainCarts/Commands) を参照してください。

{% include related/TrainCarts.md %}
