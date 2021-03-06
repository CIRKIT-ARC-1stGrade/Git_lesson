# BasicCommands  

知らないと逆に何もできないレベルのこととか書いてます  
リンク先のサイト見るよりもこっちを先に見たほうが良いかもしれない  

「基本の『き』」だけでも覚えてください。

## 基本の「き」  
最も頻繁に使うコマンド達です  
これだけ覚えられていれば、そこまで苦労することもないです。

基本的にGitリポジトリ(作業場)の内容を変更したら、  
1. `git add [files]`  
   [files] ←中身いじったりしたファイル・ディレクトリ  
2. `git commmit`  
   エディタが起動するので、一行目には変更した概要、二行目は開けて、三行目に詳細を書いて保存＆終了  
3. `git push`  (masterにpushする場合)  
   もしくは`git push [branch] [remote]`  
   コミット内容をリモートのリポジトリに同期  
   要はオンラインで見る方(github側)を更新する感じ  

1~3 の操作をすると、git に作業記録が残り、かつリモート側にも反映されます。  
実のところ、`push` は毎回する必要はありません。むしろ`push`すると後からコミットを修正するのが大変なので  
私自身は少し待ってからにしています。ただ`push`し忘れるといつまでもリモートに反映されないままなので注意。  
また、リモート側の状態をローカル(手元の作業場)に持ってくるときは、  
`git pull` (masterに居る場合)  
もしくは`git pull [branch] [remote]`  

作業を始める前に一度`pull`しておくことをおすすめします。  

## 基本の「ほ」  
### 新しくリポジトリを作成するとき  
0. リモートの方で新しくリポジトリを作成しとく  
1. `mkdir [リポジトリ名]`  
2. `cd [リポジトリ名]`  
3. `echo "# [リポジトリ名]" >> README.md`  
4. `git init`  
5. `git add README.md`  
6. `git commit -m "first commit"`  
7. `git remote add origin https://github.com/[アカウント名orグループ名]/[リポジトリ名].git`  
8. `git push -u origin master`  

リモートの方の確認してちゃんと作成されてたら完了  

### 既存のリポジトリを導入するとき  

`git clone https://github.com/[アカウント名orグループ名]/[リポジトリ名].git`

## 基本の「ん」  
### 「あ、前のコミットの状態に戻したいなあ（唐突）」っていうとき  
 `git reset --hard HEAD` 
 
 で最後にコミットしたときの状態に戻ります。  
### 「あ、コードを修正けどうまく行くか自信ない」「これ開発の方針変わるやつやん怖いなあ」ていうとき  
 1. `git branch <新しいブランチの名前>`  
 2. `git chechout <今作ったブランチの名前>`  
 
 とすると新しいブランチ（歴史の枝分かれ、別の世界線、仮想状態など解釈は各個人に任せます）ができ、  
 開発が進んでいく過程を枝分かれさせることが出来ます  
 ブランチは、新しく機能を追加するときなど  
 **まとまった作業を始めるときに作成するようにしましょう**   
 積極的にブランチを分けて作業するようにクセをつけると、取り返しのつかないことになりにくいです  
 保険をかける感じにも近いですかね  
 このあとそれぞれのブランチをマージ（合流）させることが出来ます  
 マージについてはまた後日  
  
### 「この変更いらなくない？、取り消したいなあ。。」  
`git revert [HEAD or commitのid などでcommitを指定]`  
    
とすると指定したcommitが取り消されます  
    
こういう機能があるのでcommitは  
作業の区切りがいいところで、  
こまめにすることをおすすめします  

**ここまででgitの基本です。**  
**さらに理解を深めたい方は[Links.md](https://github.com/tanacchi/GitLesson/blob/master/Links.md)を**  
**参照してください**  
