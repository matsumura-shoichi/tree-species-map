# 高分解能（0.5m）標高データによる立体地図に樹種ポリゴン（ベクトルタイルタイル）を重ねる

　本リポジトリは、**MapLibre GL JS** を用いて、林野庁等が公開している樹種ポリゴンデータを  
 高分解能（0.5m）標高データによる立体地図上に重ね合わせて可視化するサンプルサイトです。  

---
# Tree Species Map

**公開サイト**: [https://matsumura-shoichi.github.io/tree-species-map/](https://matsumura-shoichi.github.io/tree-species-map/)

# [![サンプル動画](https://youtu.be/I8ZvEXq2LKU/0.jpg)](https://youtu.be/I8ZvEXq2LKU>)


## 概要

本サイトでは **MapLibre GL JS** を使用しています。  
MapLibre GL JS は、オープンソースの WebGL ベースの地図描画ライブラリで、  
自由に地図スタイルを定義したり、ベクトルタイルやラスタタイルを  
高速に描画できるのが特徴です。  

本サイトでは以下の要素を実装しています：  
- 3D地形表示（Terrain-RGB タイル使用）  
- 樹種ポリゴンの半透明オーバーレイ表示  
- ポリゴンへのマウスオーバーで樹種名表示  
- 各地域ごとの専用ページ（栃木県、兵庫県、高知県、滋賀県、神奈川県、長崎県、愛媛県、能登地域、長岡地域）  
- 親ページ（index.html）から地域を選択可能  

---

## 操作方法

- **ドラッグ**：地図の移動  
- **マウスホイール / ピンチ操作**：拡大・縮小  
- **右ドラッグ（Shift+ドラッグでも可）**：3D視点の回転  
- **ダブルクリック**：その地点を中心に拡大  
- **ポリゴンにマウスオーバー**：樹種名がポップアップで表示される  

---

## ページ構成

- `index.html` : 地域選択用トップページ  
- `tochigi.html` : 栃木県表示ページ  
- `hyogo.html` : 兵庫県表示ページ  
- `kochi.html` : 高知県表示ページ  
- `shiga.html` : 滋賀県表示ページ  
- `kanagawa.html` : 神奈川県表示ページ  
- `nagasaki.html` : 長崎県表示ページ  
- `ehime.html` : 愛媛県表示ページ  
- `noto.html` : 能登地域（2024）表示ページ  
- `nagaoka.html` : 長岡地域（2024）表示ページ  

---

## 注意点

- 標高データのある場所とない場所の差が極端に大きく、絶壁状に見えます。絶壁の上側を使用してください。
- 栃木県、兵庫県、高知県を除く県、地域では、特定のズームレベルのみ樹種レイヤーが表示されます。このため、立体表示すると視点の移動や拡大縮小によって樹種レイヤーが見えたり、見えなかったりします。
- 神奈川県のみ、DEMではなく、DSMとなっています（DSMがTearrrainRGBタイル形式で公開されていたため。）。建物等にも注目してください。
- 樹種ポリゴンがベクトルタイルで公開されている地域であっても、DEMがタイル形式で公開されていない場所については作成しませんでした。

## 使用データ・出典

- 背景地図：  
 [国土地理院 地理院タイル（標準地図・シームレス空中写真）]
 https://maps.gsi.go.jp/development/ichiran.html)  
 


- 樹種および地形：  

 〇栃木県
 栃木県森林資源データ
 栃木県「樹種ポリゴン」
 　https://www.geospatial.jp/ckan/dataset/tree_species_tochigi
 栃木県「数値標高モデル(DEM)0.5m」terrainRGB
 　https://rinya-tochigi.geospatial.jp/2023/rinya/tile/terrainRGB
 
 〇兵庫県
 兵庫県「樹種ポリゴン」
  https://www.geospatial.jp/ckan/dataset/tree_species_hyogo
 兵庫県50㎝ メッシュDEM（xyzタイル）
 　https://www.geospatial.jp/ckan/dataset/dem05_hyogo
 
 〇高知県
 高知県森林資源データ
 高知県「樹種ポリゴン」
 　https://www.geospatial.jp/ckan/dataset/tree_species_kochi
 高知県「数値標高モデル(DEM)0.5m」
 　https://www.geospatial.jp/ckan/dataset/dem05_kochi
 
 〇滋賀県
 滋賀県・DEM/微地形表現図/DCHM/林相識別図/樹種ポリゴン（林野庁加工）
 　https://www.geospatial.jp/ckan/dataset/rinya-shiga-maptiles
 
 〇神奈川県
 神奈川県・DEM/DSM/DCHM/林相識別図/樹種ポリゴン（林野庁加工）
 　https://www.geospatial.jp/ckan/dataset/rinya-kanagawa-maptiles2
 
 〇長崎県
 長崎県・微地形表現図/DEM/林相識別図/樹種ポリゴン（林野庁加工）
 　https://www.geospatial.jp/ckan/dataset/rinya-nagasaki-maptiles
 
 〇愛媛県
 愛媛県・DEM/樹種ポリゴン（林野庁加工）
 　https://www.geospatial.jp/ckan/dataset/rinya-ehime-maptiles
 
 〇能登地域（2024）
 林野庁・樹種ポリゴン（能登地域2024）
 　https://www.geospatial.jp/ckan/dataset/rinya-treespecies-noto2024
 林野庁・数値標高モデルDEM0.5m（能登地域2024）
 　https://www.geospatial.jp/ckan/dataset/rinya-dem-noto2024
 
 〇長岡地域（2024）
 林野庁・樹種ポリゴン（長岡地域2024）
 　https://www.geospatial.jp/ckan/dataset/rinya-treespeceies-nagaoka2024
 林野庁・数値標高モデルDEM0.5m（長岡地域2024）
 　https://www.geospatial.jp/ckan/dataset/rinya-dem-nagaoka2024

---
