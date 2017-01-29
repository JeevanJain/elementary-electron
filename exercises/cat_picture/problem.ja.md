# 猫の写真

これで作業をする土台が完成したので、新しい機能を実装することができます。
これから追加する新しい機能、それは「猫の写真を描画する」です。

この新しい機能を実装するのに、0からコードを書いても良いです。しかし、一般的なプログラミングのタスクと同様に他の誰かが既にコードを書いてくれているようです。Node.js は開発者に作成したコードのまとまりをパッケージ化して簡単に再利用する方法を提供しており、そのようなパッケージ(Node.js からは "modules" と呼ばれています)を作成・ダウンロード・インストールを行うための `npm` と呼ばれるプログラムも提供しています。もしあなたが R 言語に精通しているならば、`install.packages()` コマンドに非常に近いものといえば分かりやすいかもしれません。

それでは本題に戻ります。輝く猫の写真をアプリに追加しましょう。これを作るのに、`cat-picture` と呼ばれるモジュールを npmjs.org からインストールして使ってみましょう。このモジュールは、ウェブページに猫の写真を追加するためのものです。

この `cat-picture` モジュールをダウンロード・インストールするのに、`npm` コマンドを使います。しかし、その作業をする前に、このアプリケーションは何をするためのものか、Node.js にもう少し情報を伝えてみましょう。これを行うベストな方法は、_あなたのモジュール_ を作成することです！

自分のモジュールを作成するには、私たちのモジュールに関するいくつかの詳細、例えば依存している他のモジュールのリストなどを含んだ `package.json`というファイルを作成する必要があります。そして、`npm` は私たちのかわりにこれを行ってくれます！

`npm init`コマンドを実行してみてください。このコマンドを実行すると、いくつかの質問が表示されるので回答してください。また、 答えがわからない場合は "enter" で飛ばすとデフォルトの回答がセットされます。

このコマンドが完了すると、コマンドを実行したディレクトリで `package.json` という名前のファイルが生成されます。チェックしてみてください！エディタで `package.json` を開いてみましょう。

次に、このコマンドを実行してみてください: `npm install cat-picture --save`

この一連の流れは、`cat-picture` モジュールを `node_modules` という名前のフォルダにダウンロードし、cat-picture を `package.json`に追加するというものです。もし今 `package.json` をエディタで改めて開いてみると `cat-picture` の記述を確認することができるでしょう。

さて、モジュールのインストールが完了したので、いよいよアプリケーションで実際に使ってみましょう。まずは、 `index.html` ファイルを作成し、下記の一行を `<body>` の中、かつ `<h1>` の _あと_ に追加してみてください:

```
<script type="text/javascript" src="index.js"></script>
```

完了したら、同じディレクトリに `index.js` を追加し、エディタで開いて下記の一行を追加してみてください:

```
require('cat-picture')
```

これで、`electron app.js` を実行してアプリを開くと、猫の写真を見ることができます！

このチャレンジが完了したら、`elementary-electron verify` を実行してください。