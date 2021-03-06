# 100 Days Of Code - 学習ログ

### 0 日目: 2020 年 5 月 3 日

- 今日の進捗: Udemy で Nuxt.js の入門コースに取り掛かる
- 思ったこと: フレームワークなので各フォルダが何の役割なのか基礎をちゃんと覚えていく
- リンク [Udemy Nuxt JS 入門決定版！Vue.js のフレームワーク Nuxt JS の基本から Firebase と連携した SPA の開発まで](https://www.udemy.com/course/nuxtjs-the-complete-guide/)

### 1 日目: 2020 年 5 月 4 日

- 今日の進捗: Udemy Nuxt.js 入門 vuex を学ぶ
- 思ったこと:nuxt.js を最小限の構成で構築するとの演習が理解に役立った。
- リンク [Udemy Nuxt JS 入門決定版！](https://www.udemy.com/course/nuxtjs-the-complete-guide/)

### 2 日目: 2020 年 5 月 5 日

- 今日の進捗: Udemy Nuxt.js 入門 vuex を学ぶ
- 思ったこと: vuex を使うことで親子間のデータ受け渡しに悩まなくてすむ、Udemy 教材一通り完了。次の勉強はどれにしようか悩む。
- リンク [Udemy Nuxt JS 入門決定版！](https://www.udemy.com/course/nuxtjs-the-complete-guide/)

### 3 日目: 2020 年 5 月 6 日

- 進捗: Vue&Laravel 設定完了、これからガシガシコード書いてく
- 思ったこと:
  - Udemy のこの教材お勧め。説明がゆっくり、丁寧、コードが Github にレッスン単位に載っている！
  - Vue.js １ファイルで html/javascript/css が１つのファイル → 関心の分離について 注意すべき重要な点の 1 つは、関心事項の分離がファイルタイプの分離と等しくないことです。 現代の UI 開発では、コードベースを互いに織り交ぜる 3 つの巨大なレイヤーに分割するのではなく、それらを疎結合なコンポーネントに分割して構成する方がはるかに理にかなっています。コンポーネントの内部では、そのテンプレート、ロジック、スタイルが本質的に結合されており、実際にそれらを配置することで、コンポーネントがより一貫性と保守性に優れています。
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 4 日目: 2020 年 5 月 7 日

- 進捗: Postman を使った API 動作確認の実施
- 思ったこと:

  - laravel seed 便利
  - api で get するときの URL の最初に/をつける

  ```php
    axios
      .get(`/api/bookables/${this.$route.params.id}`)
      .then(response => (this.bookable = response.data));
  ```

  - gitignore が反映されなくてキャッシュが残っていることが問題だった(https://qiita.com/fuwamaki/items/3ed021163e50beab7154)

- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 5 日目: 2020 年 5 月 8 日

- 進捗: vue と api の連携
- 思ったこと:
  - apiResource を使うとまとめて定義ができる。また使いたい api だけ only で定義できる
  ```
  Route::apiResource('bookables', 'Api\BookableController')->only('index', 'show');
  ```
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 6 日目: 2020 年 5 月 9 日

- 進捗:
- 思ったこと:
  - API Resources を使うとフィルターができる。JsonResource を使ったときにデータが data でラッピングされるため注意が必要。(https://laravel.com/docs/7.x/eloquent-resources) 以下を Providers に記載することでデータラッピングを外せる
  ```
   JsonResource::withoutWrapping();
  ```
  - install debugger laravel
  ```
  composer require barryvdh/laravel-debugbar --dev
  ```
  - Laravel Collection とは、リスト形式でデータを格納できるラッパーのことを指します。 Laravel collection の使い方【初心者向け】｜ TECH PLAY Magazine ［テックプレイマガジン］ https://techplay.jp/column/630
  - MassAssignment http://laravel.hatenablog.com/entry/2013/10/24/005050
  - postman で validate エラーのチェックをするときに Postman>Headers>KEY=Accept, Value=application/json を設定する
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 7 日目: 2020 年 5 月 10 日

- 進捗:validation と form からのデータ取得
- 思ったこと:
  - Laravel は fat にならないような工夫がされている
  - レスポンスコード 422 https://developer.mozilla.org/ja/docs/Web/HTTP/Status/422
    > The HyperText Transfer Protocol (HTTP) の 422 Unprocessable Entity 応答状態コードは、サーバーが要求本文のコンテンツ型を理解でき、要求本文の構文が正しいものの、中に含まれている指示が処理できなかったことを表します。
  - laravel uuid ランダムな文字列 https://www.webopixel.net/php/1380.html。uuidを設定するときに該当のmodelに自動インクリメントしないと文字列設定を追記
- ````
  public function getIncrementing()
    {
        return false;
    }

    public function getKeyType()
    {
        return 'string';
    }```
  ````

- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 8 日目: 2020 年 5 月 11 日

- 進捗:Resource,filter
- 思ったこと:
  - vue.js filter テキストフォーマットの整形 https://jp.vuejs.org/v2/guide/filters.html
  - 細かいスペルミスで詰まったりしている。デバッグが勉強になるといえば勉強になる。
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 9 日目: 2020 年 5 月 12 日

- 進捗:done Section 7: ReviewList Component
- 思ったこと:
  - global component -> app.js に登録する
  - font awesome を利用するときに app.scss に登録が必要 https://fontawesome.com/how-to-use/on-the-web/using-with/sass
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 10 日目: 2020 年 5 月 13 日

- 進捗:Review Component フロント部分を構築中
- 思ったこと:
  - props nameが違っていてエラー発生。細かいミスをすぐに解決できてよかった
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)
