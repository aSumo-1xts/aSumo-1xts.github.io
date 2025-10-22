---
layout: doc

emoji: 🧮
title: MATLAB小技集
description: ｱｽﾓのﾒﾓﾗﾝﾀﾞ、ｱｽﾓﾗﾝﾀﾞ

date: 2025-10-23
permalink: "https://aSumoranda.com/posts/07-MATLABtips.html"

prev: false
next: false

tags:
  - matlab

hidden: true
---

## はじめに

MATLABのちょっとした所作をすぐ忘れるので、思い出し次第ここに書き連ねます。

## 日付の生成

[`datestr()`](https://jp.mathworks.com/help/matlab/ref/datetime.datestr.html)が非推奨なので、[`datetime()`](https://jp.mathworks.com/help/matlab/ref/datetime.html)を使う。

```matlab
date        = datetime('now');
date.Format = 'MMdd-HHmm';      % フォーマットは適宜変更
dateStr     = string(date);
```

## プロット関連

### x軸（あるいはx軸に平行な線）を描く

```matlab
yline(0, 'k-', 'LineWidth', 1.5);
```

もちろん、y軸を描く場合は`xline()`を使う。

### 既定のカラーパレットを呼び出す

二次元プロットの`Color`を何も指定しないと独特の青、橙、黄、…みたいな色になるが、これらの色を恣意的に呼び出す。

```matlab
RGB = orderedcolors("gem");
H = rgb2hex(RGB);

% 例: H(1) = "#1171BE"
```
