---
layout: doc

emoji: ☁️
title: tiny11builder後のOneDrive導入
description: ｱｽﾓのﾒﾓﾗﾝﾀﾞ、ｱｽﾓﾗﾝﾀﾞ

date: 2025-10-24
permalink: "https://aSumoranda.com/posts/09-tiny11-onedrive.html"

prev: false
next: false

tags:
  - trouble

hidden: true
---

## はじめに

[tiny11builder](https://github.com/ntdevlabs/tiny11builder)を使ってシンプルなWindows11を手に入れたまでは良かったのですが、OneDriveはやっぱり欲しいな…と思って自分でインストールしたところ躓きました。ことの顛末を記しておきます。

## 環境

Windows11 25H2

## 症状

OneDriveをインストールして実行してみても同期が始まらず、どうもインターネットと接続される気配が無い。wingetでもインストーラでもダメで、アンインストール・再インストールしてもダメ。

## 解決

リポジトリを見に行ったら[同じ悩みの人がissueを立てていて](https://github.com/ntdevlabs/tiny11builder/issues/467)、コントリビュータの方が解決策を提示してくれていました。

> インストールしたあと、忘れずに再び有効化してください：
>
> 1. レジストリエディターを開く
> 2. `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\OneDrive`へ行く
> 3. `DisableFileSyncNGSC`の値を0にする
> 4. 必要に応じて再起動

なるほど、tiny11builderはOneDriveを削除するのみならず同期まで止めていたのか。これで無事にOneDriveが同期されました。

![[image/Pasted image 20251008005423.png]]
