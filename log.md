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
  - props name が違っていてエラー発生。細かいミスをすぐに解決できてよかった
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 11 日目: 2020 年 5 月 14 日

- 進捗:Review Component フロント部分を構築中
- 思ったこと:
  - 子から親へのコンポーネント間のデータ受け渡し emit https://orizuru.io/blog/vue-js/vue_emit-props/
  - https://jp.vuejs.org/v2/guide/components-custom-events.html
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 12 日目: 2020 年 5 月 15 日

- 進捗:Review Component フロント部分を構築中
- 思ったこと:
  - 仕事がたてこんで勉強する時間をあまりとれなかったけど、少しでも毎日コードを書き続けていくことをしよう
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### 13 日目: 2020 年 5 月 16 日

- 進捗:作りたいアプリの基盤構築中
- 思ったこと:
  - Vue,Laravel 基盤部分の構成ってあまり理解できていない
  - VueRouter とか何度も手動で構築すると理解が深まる
- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### Day 14: 2020/05/17

- Today's Progress : Prototyping the app
- Thoughts :
  - I was able to use what I learned in the Udemy course to code the prototype's simple logic without much hesitation.
  - I was somewhat confused about the difference between Vue and PHP array writing
- Link to work
  [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### Day 15: 2020/05/18

- Today's Progress : Prototyping the app
- Thoughts :
  - When I wanted to get data randomly from an array, I used Laravel's collection feature and it was very easy to do!
- I could easily handle responsive design with vuetify grid based on this article! https://reffect.co.jp/vue/vuetify-grid-system
- Link to work
  [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### Day 16: 2020/05/19

- Today's Progress : Prototyping the app
- Thoughts :
  - Be careful with types when retrieving data from query parameters
  - I don't understand vue mount, created
- Link to work
  [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### Day 17: 2020/05/20

- Today's Progress : Prototyping the app
- Thoughts :
  - In created:, the function will not be called unless this.function name() is used.
  - Add array vm.\$set(vm.items, indexOfItem, newValue)
    [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)

### Day 18: 2020/05/21

- Today's Progress : Prototyping the app
- Thoughts :
  - I'm stuck on a common beginner's mistake.
  - However, when defining a component, data must be declared as a function that returns the initial data object. Why? Because there will be many instances created using the same definition.

[Vue.js Common Beginner Gotchas](https://vuejs.org/2016/02/06/common-gotchas/)

### Day 19: 2020/05/22

- Today's Progress : Prototyping the app
- Thoughts :
- FileName -> PascalCase:UserList.vue
- HTML -> Kebab case: <user-list>
- JS -> Camel case: userList
  [[Vue.js] ケバブケースとかキャメルケースとかパスカルケースとか](https://qiita.com/kozzzz/items/5f36a2a830c187a75a51)
