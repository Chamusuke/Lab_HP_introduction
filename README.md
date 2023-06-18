# **HPの運用**
  Editor: Hayato Nakamura   
  2023/05/04~  
  UTF-8  
  GitHub: https://github.com/Chamusuke/Lab_HP_introduction
  ***
  ## **！デバック時の注意**   
  **メンテナンス性を重視し、よく変更する部分は.txtファイルの書き換えのみで変更できるようにした．**  

  - <span style="color: green; ">**newsとthemeは.txtファイル内を変更するだけでHTMLに反映可能．**</span>  
- <span style="color: green; ">**メンバー変更のみ、index.html等を変更する必要あり．**</span>  

セキュリティ上の理由から、一般的にはローカルファイルの直接読み込みは制限されており、vscodeでのデバックに拡張機能が必要となる．  

<span style="color: red; ">**注意：デバックは、ローカルサーバーを使用して起動する．**</span>  
<span style="color: red; ">**VScodeの拡張機能からLive Serverをインストール**</span>  
<span style="color: red; ">**htmlファイルを開いた状態で画面右下のGO Liveを押し、ローカルサーバーからindex.htmlを読み込んでデバックを行う.**</span>  
***

  
  
## **内容**
- [ディレクトリ・ファイル構成](#sec1)
- [メンバーの変更](#sec2)
- [ニュースの更新](#sec3)
- [研究テーマの変更](#sec4)
- [Publicationの追加](#sec5)


---
<a id="sec1"></a>
## **ディレクトリ・ファイル構成**

 **必要なファイルのみピックアップ**  
<span style="color: red; "> **！デバック時は、サーバーから以下のディレクトリを任意の場所にダウンロードして編集すること**</span>    
 mitsu.sd.ac.jp/home直下　　
```
home:.
│  index jp.html          -->日本語ホームページ  
│  index.html             -->英語ホームページ  
│  mitsu.png              -->サイトのタグ画像  
│  README.md                
│  readme.txt  
│  
├─.vscode  
│      launch.json  
├─contents  
│      member.html          -->過去のメンバー  
│      publication.html     -->論文  
├─css  
│      animate.css  
│      animation.css  
│      bootstrap.min.css  
│      font-awesome.css  
│      style-1.css          -->publication.html,member.htmlのスタイル  
│      style.css            -->index.htmlのスタイル  
│      style_jp.css         -->index_jp.htmlのスタイル  
├─fonts  
│  └─fontawesome-free-6.4.0-web  
├─img  
│  │  mail.jpg  
│  │  mail.png  
│  │  mission.jpg  
│  │  preparing.jpg  
│  │  slide1.jpg  
│  │  slide2.jpg  
│  │  slide3.jpg  
│  │  slide4.jpg   
│  │  slide4_1000.jpg  
│  │  slide4_1500.jpg  
│  │  slide4_600.jpg  
│  ├─people               -->メンバー画像  
│  │      brian.jpg  
│  │      clarissa.jpg  
│  │      empty.jpg  
│  │      hamada.jpg  
│  │      hasegawa.jpg  
│  │      ikeda.jpg  
│  │      kato.jpg  
│  │      kutsu.jpg  
│  │      mitsukura.jpg  
│  │      nakada.jpg  
│  │      nakamoto.jpg  
│  │      nakamura.jpg
│  │      nashimoto.jpg
│  │      ogawa.jpg
│  │      poul.jpg
│  │      rin.jpg
│  │      sato.jpg
│  │      shinozaki.jpg
│  │      suzuki.jpg
│  │      tsukahara.jpg
│  │      yamamoto.jpg
│  └─theme              -->研究のテーマ画像
├─js
│  │  bootstrap.min.js
│  │  custom.js
│  │  html5element.js
│  │  html5shiv.js
│  │  jquery-1.11.0.min.js
│  │  jquery-scrolltofixed.js
│  │  jquery.easing.1.3.js
│  │  jquery.isotope.js
│  │  jquery.nav.js
│  │  news_read.js          -->txtファイルの読み取りとindex.html内のニュース内容に反映
│  │  news_read_jp.js       -->txtファイルの読み取りとindex_jp.html内のニュース内容に反映
│  │  respond-1.1.0.min.js
│  │  theme_read.js         -->txtファイルの読み取りとindex.html内のテーマ内容に反映
│  │  theme_read_jp.js      -->txtファイルの読み取りとindex_jp.html内のテーマ内容に反映
│  │  wow.js
│  └─fancybox
└─txt
    │  test.txt
    │
    ├─news
    │      news1.txt        -->英語用のニュース内容
    │      news1_jp.txt     -->日本語用のニュース内容
    │      news2.txt
    │      news2_jp.txt
    │      news3.txt
    │      news3_jp.txt
    │      news4.txt
    │      news4_jp.txt
    │
    ├─team
    │      team1.txt
    │
    └─theme
            theme_1.txt      -->英語用の研究テーマ内容
            theme_1_jp.txt   -->日本語用の研究テーマ内容
            theme_2.txt
            theme_2_jp.txt
            theme_3.txt
            theme_3_jp.txt
            theme_4.txt
            theme_4_jp.txt
            theme_5.txt
            theme_5_jp.txt
            theme_6.txt
            theme_6_jp.txt
 ``` 

***
<a id="sec2"></a>
## **メンバーの更新・変更**
htmlファイルの変更を行う（日本語版と英語版両方）  

<span style="color: red; ">１列５人配置</span>

### **該当ファイル**
- 内容、スタイルの変更  
  home/ index.html  
  home/ index_jp.html
  home/ contents/ member.html

- 画像の差し替え  
  home/ img/ peaple/ *.jpg  
  *は、ワイルドカード　　

### **記入例**
**列のクラス**
```
    <!--O列目-->　
    <div class="row-50"></div>
    <div class="row justify-content-center">
    |  <!--ここに五人分のメンバークラスをはさむ　
    |  足りない場合は空のクラスを作り調節する-->
    |
    </div>
```

**メンバークラス**  
  1. 参照する画像ファイルの変更
  2. 名前（英語）の変更
  3. 名前（日本語）の変更
  4. 学年の変更
  ```
<!--------------------------------------------------------------------->
      <div class="col-sm-3 m-sm-auto">
        <div class="row align-items-center">
          <div class="team-image">
            <img alt="image" class="img-fluid rounded-circle" src="./img/people/ファイル名">  
          </div>
          <div class="team-name">
            <h10>名前（英語）<br>
              名前（日本語）<br>
            <h11>学年 </h11></h10>
          </div>
        </div>
      </div>
   ```
   ```   
<!--Ver.空のメンバークラス-->
<!--------------------------------------------------------------------->
      <div class="col-sm-3 m-sm-auto">
        <div class="row align-items-center">
          <div class="team-image">
          </div>
          <div class="team-name">
          </div>
        </div>
      </div> 
<!--------------------------------------------------------------------->     
```

**Old memberの差し替え**
```
                    <tr>
                        <td rowspan='7'>20〇〇年度</td>
                        <td rowspan="4">修士</td>

                        <td>名前1</td>

                    </tr>

                    <tr>
                        <td>名前2</td>
                    </tr>

                    <tr>
                        <td>名前3</td>
                    </tr>
        ..略
------------------------------------------------------------------
                    <tr>
                        <td rowspan='4'>学士</td>

                        <td>名前4</td>

                    </tr>

                    <tr>
                        <td>名前5</td>
                    </tr>
          ..略

```


***
<a id="sec3"></a>
## **ニュースの更新**
表示する内容は、home/txt/newsディレクトリ直下のtxtファイルに記述する  
運用しやすくするため、txtファイルをJavaScriptで読み取り、各HTMLに反映させている．  
**<span style="color: red; ">行ごとに文字列を取り出して、それぞれのクラスに代入している</span>**

### 該当ファイル
- home/txt/news/*.txt   
*は、ワイルドカード調べてみてね  

### 記入例
```
Apr
-----------------------------------
New Semester
-----------------------------------
April 1, 2023
-----------------------------------
新学期を迎えました．
```

***
<a id="sec4"></a>
## **研究テーマの変更**
表示する内容は、home/txt/themeディレクトリ直下のtxtファイルに記述する．  
運用しやすくするため、txtファイルをJavaScriptで読み取り、各HTMLに反映させている．  
**<span style="color: red; ">行ごとに文字列を取り出して、それぞれのクラスに代入している</span>**

## **該当ファイル**
- **画像の差し替え**  
home/img/theme直下のファイルを変更する．  
- **テキストの差し替え**  
home/txt/theme直下のファイルを変更する．

## **記入例**
- 1行目：タイトル
- 2行目：読み込まない
- 3行目以降：本文　注意:改行せず表示される
```
新しいバイオマーカー
------２行目は読み込まない-----------------------------
センシング技術やアルゴリズムを開発し、新たなバイオマーカーを作製しています。
新たなバイオマーカーは、病理解明、治療への新しいアプローチとなります．
```

***
<a id="sec5"></a>
## **Publicationの追加**
