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

### Day 20: 2020/05/23

- Today's Progress : Review of Vue.js Basics
- Thoughts :
  - strikeout 取り消し線
  -
  [[Vue.js] ケバブケースとかキャメルケースとかパスカルケースとか](https://qiita.com/kozzzz/items/5f36a2a830c187a75a51)

### Day 21: 2020/05/24

- Today's Progress : Udemy Vue&Laravel
- Thoughts :
  - Eloquent's boot.Eloquent is an ORM in Laravel, but the first time it is called, it calls a static method called boot to do the initialization. As for how to use this BOOT, the manual site has set up a global scope and events.

### Day 22: 2020/05/25

- Today's Progress : Prototype App
- Thoughts :
- よく言う「N+1」問題というやつ。
  クエリを 1 回+N 回発行してしまうと、大規模なデータになるほど、データをとるのにものすごく時間がかかってしまってタイムアウトになってしまうこともある。これを避けるため、先にリレーションデータも取得しておくのが "Eager loading" であり、Eloquent では with メソドを使う。

```php
//lazy loading
$books = App\Book::all(); //クエリを1回発行したあと、

foreach ($books as $book) {
    echo $book->author->name; //booksの冊数分（N回）だけ発行される。
}

//Eager loading
$books = App\Book::with('author')->get(); //クエリが発行されるのは2回だけ

foreach ($books as $book) {
    echo $book->author->name;
}
```

[[Laravel] Eloquent リレーションと Eager Loading](https://qiita.com/shosho/items/abf6423283f761703d01)

- vuex getter にコンポーネントからアクセスするとき
  UserList コンポーネントの中で先ほど実行していた処理を削除し、getters を使った処理に変更を行います。Getters には this.\$store.getters でアクセスすることができます。
  https://reffect.co.jp/vue/understaind-vue-basic#Getters

```javascript
computed:{
	users: function(){
		return this.$store.getters.users;
	}
}
```

### Day 23: 2020/05/25

- Today's Progress : Prototype App
- Thoughts :
- vuex state,getter の設定周りをコーディング。computed property と Vuex getter は機能的にはほとんど同じで、computed property はその component でしか使えないのに対し、getter はどの component からも使えるという違いがあります。複数のコンポーネントで同じ computed property を定義すると無駄なので store の getter として定義する、という感じでいいと思います。

### Day 24: 2020/05/26

- Today's Progress : Vuex getters
- Thoughts :
- ゲッターは第 2 引数として他のゲッターを受け取ります:
  ```
  getters: {
  // ...
  doneTodosCount: (state, getters) => {
    return getters.doneTodos.length
  }
  }
  ```

### Day 25: 2020/05/27

- Today's Progress : prototype app
- Thoughts :コンポーネントはまだローカルステートを持つことできる
  Vuex を使うということは、全ての状態を Vuex の中に置くべき、というわけではありません。多くの状態を Vuex に置くことで、状態の変更がさらに明示的、デバッグ可能になりますが、ときにはコードを冗長でまわりくどいものにします。状態の一部がひとつのコンポーネントだけに属している場合は、それをローカルの状態として残しておくとよいでしょう。あなたは、トレードオフを考慮した上で、あなたのアプリの開発ニーズに合った決定をすべきです。
- links:https://vuex.vuejs.org/ja/guide/state.html

### Day 26: 2020/05/28

- Today's Progress : vuex & v-model
- Thoughts :computed のなかで set と get を設定することで v-model を vuex と利用することができる
- links: https://vuex.vuejs.org/guide/forms.html

### Day 27: 2020/05/29

- Today's Progress : vuex
- Thoughts :vuex を適用すると v-select とか v-model 系が書き直しになる。Qiita にはサンプルが少ないが公式には載っていた。
- links: https://vuex.vuejs.org/guide/forms.html

### Day 28: 2020/05/30

- Today's Progress : vuex
- Thoughts :非同期に state を書き換えたいなら action を使う。ajax や setTimeout や Firebase のような非同期処理の後に state を書き換えたい場合には actions に非同期の関数を登録します。
- links: https://vuex.vuejs.org/guide/forms.html

### Day 29: 2020/05/31

- Today's Progress : vue router
- Thoughts :ページ遷移後のデータの取得を対応。動的パラメータが簡単に取得できてよかった。
- youtube の埋め込み vue だと簡単にできそう https://qiita.com/norton0209/items/ba3e46342a0dbed065e2
- links: https://vuex.vuejs.org/guide/forms.html

### Day 30: 2020/06/01

- Today's Progress : prototype app
- Thoughts : netlify を利用して github に push したら自動でデプロイを設定。自分が作ったアプリが動くというのはたとえシンプルなアプリでも嬉しい。
- links: https://vuex.vuejs.org/guide/forms.html

### Day 31: 2020/06/02

- Today's Progress : prototype app
- Thoughts : 急に vue-cli でコンパイルエラーが発生した。かつ原因不明で困った。node と vue-cli のアップデートをしたらとりあえず治ってよかった。
- links: https://vuex.vuejs.org/guide/forms.html

### Day 32: 2020/06/03

- Today's Progress : prototype app
- Thoughts : コンパイルエラーが再び発生 。vue-cli バージョンを上げたときに babel が古いとのこと。参考 →https://qiita.com/DaisukeNishi/items/ff36054a2d00cf81aac4
  このコマンドを実行して解決
  ```
  $ npm install --save core-js
  ```
-
- links: https://vuex.vuejs.org/guide/forms.html

### Day 33: 2020/06/04

- Today's Progress : prototype app
- Thoughts : javascript の配列を無理やり組んで対応。配列の特定インデックスの値を書き換える。

```
a = [{a:1},{b:2}]
a.splice(1, 1, {b:10})
```

- links: [2018 年 Vue.js を使ってる人には知って欲しいオブジェクトと配列の操作のベストプラクティス](https://qiita.com/kahirokunn/items/9ece44e4327946583a00)

### Day 34: 2020/06/05

- Today's Progress : prototype app
- Thoughts : 昔の for 文のまま使っているので forEach を使っていきたい…
- links: [2018 年 Vue.js を使ってる人には知って欲しいオブジェクトと配列の操作のベストプラクティス](https://qiita.com/kahirokunn/items/9ece44e4327946583a00)

### Day 35: 2020/06/06

- Today's Progress : prototype app
- Thoughts :
  - vue for 文のなかで index を使えば今何列目か取得できる
  - vue でリアクティブに配列更新をするときは splice を使う
- links: [2018 年 Vue.js を使ってる人には知って欲しいオブジェクトと配列の操作のベストプラクティス](https://qiita.com/kahirokunn/items/9ece44e4327946583a00)

### Day 36: 2020/06/07

- Today's Progress : prototype app
- Thoughts :
  - テーブル設計と同じように vuex のデータ設計も必要だと思うのだが、vuex のデータ設計の作業をなんというのだろう →Component 設計
- links: [Vuex のルールと Component 設計](https://techblog.roxx.co.jp/entry/2019/02/14/154002)

### Day 37: 2020/06/08

- Today's Progress : prototype app
- Thoughts :現職の仕事がリリース前で佳境、勉強の時間がなかなか取れない...。vuex で mutaions と actions を使い分けるよりも actions に統一してしまったほうがコードがスッキリする
- links: [Vuex のルールと Component 設計](https://techblog.roxx.co.jp/entry/2019/02/14/154002)

### Day 38: 2020/06/09

- Today's Progress : prototype app
- Thoughts :vue で配列を取り扱うときはいつもリアクティブにコーディングできているか気をつける必要がある
- links: [Vue.js は気難しい（配列編）](https://qiita.com/tmak_tsukamoto/items/e303328681f20a036530)

### Day 39: 2020/06/10

- Today's Progress : prototype app
- Thoughts :朝から晩まで仕事だったのでコーディングができなかった。座学で vue.js を勉強実施
  オブジェクトにさらにフィールドを持たせることで複数のクラスを切り替えることができます。加えて、v-bind:class ディレクティブはプレーンな class 属性と共存できます。つまり、次のようなテンプレートと:
  ```
  <div
  class="static"
  v-bind:class="{ active: isActive, 'text-danger': hasError }"
  ></div>
  ```
- links: [Vue.js](https://vuejs.org/v2/guide/class-and-style.html)

### Day 40: 2020/06/11

- Today's Progress : prototype app
- Thoughts :朝から晩まで仕事だったのでコーディングができなかった。引き続きスキマ時間に座学で vue.js を勉強実施
  Vue はプロパティの追加または削除を検出できません。Vue はインスタンスの初期化中に getter/setter の変換を行うため、全てのプロパティは Vue が変換してリアクティブにできるように data オブジェクトに存在しなければなりません。

```
  <div
  class="static"
  v-bind:class="{ active: isActive, 'text-danger': hasError }"
></div>
```

- links: [Vue.js](https://vuejs.org/v2/guide/class-and-style.html)

### Day 41: 2020/06/12

- Today's Progress : prototype app
- Thoughts :
- プロトタイプでいろいろいじったのを元々のリポジトリへ反映していくことをしていく予定。地味に面倒な作業になりそう。でもプロトタイプを作ったおかげで作りたいものがみえてきた。
- links: [Vue.js](https://vuejs.org/v2/guide/class-and-style.html)

### Day 42: 2020/06/13

- Today's Progress : prototype app
- Thoughts :
- プロトタイプで作ってきたものをベースに移植中。json を vue.js の配列に設定する箇所がどうしてもうまくいかない。なんでだろう。
- links: [Vue.js は気難しい（配列編）](https://qiita.com/tmak_tsukamoto/items/e303328681f20a036530)

### Day 43: 2020/06/14

- Today's Progress : laravel db 設定
- Thoughts :

  - app.php のタイムゾーン設定を変更する

  ```php
   'timezone' => 'Asia/Tokyo',
  ```

  - AppServiceProvider.php に最大未指定時の default 値を変更する

  ```php
  Schema::defaultStringLength(191);
  ```

  - Larave csv データを Seeder で DB に登録できた。ネット記事を参考に割と簡単にデータ登録ができた！

- links: [【Laravel】CSV ファイルのデータを Seeder で DB につっこむ](https://qiita.com/shosho/items/caf535b1df5cb8d8ae92)

### Day 44: 2020/06/15

- Today's Progress : laravel db 設定
- Thoughts :
  - laravel クエリパラメータの任意条件のときにどうやってせってするのかがわからなかった
- links: [【Laravel】CSV ファイルのデータを Seeder で DB につっこむ](https://qiita.com/shosho/items/caf535b1df5cb8d8ae92)

### Day 45: 2020/06/16

- Today's Progress : reading vue.js
- Thoughts :必須 props に必ず required: true を付ける
  必須 props には必ず required: true を付けるべきです。
  たまにあるのが、必須 props なのに default 値だけを指定して required: true を設定しないケースです。
- links: [2019 年版 Vue.js を使ってる人には必ず知っていてほしい Vue.js の武器とドキュメントに書かれていないコンポーネントやメンテナンスの際に役立つ Tips](https://qiita.com/kahirokunn/items/6b4834b9a13406535f32)

### Day 46: 2020/06/17

- Today's Progress : reading vue.js
- Thoughts :5. データプロパティでは必ず Function を返す

コンポーネントでデータを宣言する際、データプロパティには必ず function を return するようにしましょう。return しない場合、オブジェクトを返すことになり、データがすべてのコンポーネントのインスタンスで共有されてしまいます。
再利用可能で固有のオブジェクトを返すコンポーネントを作る場合がほとんどだと思いますが、データオブジェクトを function 内で return することで実現することができます。

```
// Bad
data: {
  name: 'Momoko Toyota',
  hobbies: []
}

// Good
data () {
  return {
    name: 'Momoko Toyota',
    hobbies: []
  }
}
```

- links: [Vue 開発者のための Vue.js ベストプラクティス集 15 選](https://qiita.com/mtoyopet/items/87a32d8e3497c5421727)

### Day 47: 2020/06/18

- Today's Progress : vuex+select form
- Thoughts :vuex+select の実装でハマった。表示用のデータと select して active になったデータとを分けることで vuex で対応することができた

- links:[CodePen Home Vue Select With Vuex With Custom Attribute](https://codepen.io/fromarm4/pen/xzMyKv)

### Day 48: 2020/06/19

- Today's Progress : vuex+select form
- Thoughts :vuex+select の復習

  ```
  <v-select
    multiple
    label="email"
    @input="updateValue($event, 'active_peaple')"
    :options="$store.state.people"
    :value="$store.state.form.active_peaple"
  ></v-select>
  ```

- links:[CodePen Home Vue Select With Vuex With Custom Attribute](https://codepen.io/fromarm4/pen/xzMyKv)

### Day 49: 2020/06/20

- Today's Progress : v-switch
- Thoughts :vuex と v-switch の組み合わせがうまく動かない…

### Day 50: 2020/06/21

- Today's Progress : where 条件の設定
- Thoughts :
  - vue の css 適用の仕方

```
<style lang="scss" scoped>
.v-toolbar__title {
  overflow: visible !important;
  margin-right: 50px !important;
}
</style>
```

また、確実にスタイルを適用させるために、Vuetify で生成されたクラスのスタイルを修正する場合は、!important をつけましょう。これをつけなければ、スタイルが適用されないことがあります。

- laravel での where 条件。query を事前につくっておこくことで対応ができる。Controller 側で使用する Model を use で記述し、query を呼び出し、最後に get()することで条件の行を取得することが出来ます。

- links:[Laravel5.4 でさまざまな条件での絞り込み方法](https://www.willstyle.co.jp/blog/1116/)

### Day 51: 2020/06/22

- Today's Progress : where 条件の設定
- Thoughts :直接インデックス(例: arr[0] = val) を設定、または length プロパティを変更することによって配列を変更する場合 view は更新されません。同様に、Vue.js はこれらの変更を検出することはできません。常に配列のインスタンスメソッドを使用することによって配列を変更、またはそれを完全に置き換えて下さい。Vue は arr.splice(index, 1, value) のシンタックスシュガーとして、便利なメソッド arr.\$set(index, value) を提供します。
- links:[よくある初心者の落とし穴](https://jp.vuejs.org/2016/02/06/common-gotchas/)

### Day 52: 2020/06/23

- Today's Progress : vue component
- Thoughts :長くなった 1 ファイルを component 化して切り出してみたがうまい component との連携方法がわからない。component を呼び出したときにデータ表示したいが、props でデータ取得したくないときはどのようにすればよいのか悩む

### Day 53: 2020/06/24

- Today's Progress : vue component
- Thoughts :vue created,mountedのカッコの付け方を間違えて記載していてハマった。


### Day 54: 2020/06/25

- Today's Progress : vue slot
- Thoughts :slotとは親となるコンポーネント側から、子のコンポーネントのテンプレートの一部を差し込む機能 です。
スロットというと「スロットマシン」が思い浮かびますが、もともとslotの「差し込み口」という意味から派生して、コインの投入口があるスロットマシンの意味をもつようになったそうです。
- [Vue.jsのslotの機能を初心者にわかるように解説してみた](https://future-architect.github.io/articles/20200428/)

### Day 55: 2020/06/26

- Today's Progress : vue slot
- Thoughts :必須propsには必ずrequired: trueを付けるべきです。なぜこれが悪いのかというと、account propに何か入れて欲しいのに、入れ忘れた場合でも一切警告がでなく、バグ発見が困難になるからです。また、「本当に任意であるpropがどれなのか」を見分ける難易度が上がってしまいます。
- links[2019年版Vue.jsを使ってる人には必ず知っていてほしいVue.jsの武器とドキュメントに書かれていないコンポーネントやメンテナンスの際に役立つTips](https://qiita.com/kahirokunn/items/6b4834b9a13406535f32)


### Day 56: 2020/06/27

- Today's Progress : vue instance
- Thoughts :
- 通常のVueインスタンスと異なり、Vueコンポーネント内の data は data(){} で（関数的に）定義しないといけません。Vueコンポーネントは、Vueインスタンスの拡張なので、data をオブジェクト型で定義すると、元の data と干渉してしまい、意図してるように動かなくなってしまうからです。
- links[Vue.jsを100時間勉強して分かったこと](https://qiita.com/kskinaba/items/3e8887d45b11f9132012)


### Day 57: 2020/06/28

- Today's Progress : vue instance
- Thoughts :Vueコンポーネントの保存場所は、components ディレクトリを作って、そこに Shared や ServerStatus などのサブディレクトリを作って格納していく設計が一般的です。
- links[Vue.jsを100時間勉強して分かったこと](https://qiita.com/kskinaba/items/3e8887d45b11f9132012)


### Day 58: 2020/06/29

- Today's Progress : vue instance
- Thoughts :
- :class="{YOUR_CLASS: boolean}" で動的にCSSを適用できます。
```
html
<div 
    class="demo" 
    @click="attachedRed = !attachedRed"
    :class="{red: attachedRed}"></div>
```
:class を複数定義する場合は array で書きます。

- links[Vue.jsを100時間勉強して分かったこと](https://qiita.com/kskinaba/items/3e8887d45b11f9132012)


### Day 59: 2020/06/30

- Today's Progress : vue ui
- Thoughts :UIの微調整。vuetifyでUIを調整をしたがうまくレイアウトが配置できない…

### Day 60: 2020/07/01

- Today's Progress : vue component
- Thoughts :仕事が忙しくてなかなか勉強の時間が取れていない→スキマ時間にUdemyを見よう。componentが呼ばれたときにだけデータ取得をするようにしたいのだがうまくいかない

### Day 61: 2020/07/02

- Today's Progress : laravel blade
- Thoughts :laravel bladeサブビューを学んだ。サブビューの呼び出し方は下記
```
@include(‘テンプレート名, [‘キー’=>’値’]
```

### Day 62: 2020/07/03

- Today's Progress :css flexbox
- Thoughts :仕事で相対位置に設定したい値があってやりかたがそもそもわからず考え中。flex-growを勉強中
- links [CSSで中央寄せする9つの方法（縦・横にセンタリング）](https://saruwakakun.com/html-css/basic/centering)


### Day 63: 2020/07/07

- Today's Progress :laravel seeder
- Thoughts :laravel seederを修正。seederの実行方法で少し悩んだ。classを指定することで単体で実行できる
  ```
  $ php artisan db:seed --class=PhotoTableSeeder
  ```
- links [Laravelでシーダーを使う](https://qiita.com/shosho/items/b69db263a494edfe3b21)


### Day 64: 2020/07/08

- Today's Progress :css display property
- Thoughts :display: inline-block はたとえば、ソーシャルシェアボタンを横並びに配置するときだったり、メニューバー（ナビゲーションバー）でボタンを横に並べたいときなどに使う
  ```
  <div id="nav">
  　<ul>
　　   　<li>HOME</li>
　   　　<li>HTML</li>
　   　　<li>CSS</li>
  　</ul>
</div>
/* ↓id="nav"の中のulに対してCSSを適用*/
#nav ul {
  list-style-type: none; /*箇条書きのポッチを消す*/
  text-align:center /*左右中央寄せは親要素に対して指定*/
}

/* ↓id="nav"の中のulの中のliに対してCSSを適用*/
#nav ul li { 
  display: inline-block;/*inline-blockにします*/
  width: 80px;/*幅も指定できる*/
  padding: 10px 0;/*余白も指定できる*/
  margin: 10px 0;/*余白も指定できる*/
  vertical-align: middle;/*縦の表示位置も指定できる*/
  background: skyblue;/*背景を水色に*/
  font-weight: bold;/*文字を太字に*/
  color:white; /*文字色を白に*/
}
```
- links [【CSS】displayの使い方を総まとめ！inlineやblockの違いは？](https://saruwakakun.com/html-css/basic/display)

### Day 65: 2020/07/09

- Today's Progress :css display property
- Thoughts :cssの基礎をあらためて勉強中。ちょっとしたコードを試すのにjsfiddleが便利
- links [jsfiddle.net](https://jsfiddle.net/)

### Day 66: 2020/07/10
- Today's Progress :css heigt, width
- Thoughts :cssの基礎をあらためて勉強中。ちょっとしたコードを試すのにjsfiddleが便利
  - max-width, min-width,どちらもwidthの%指定と合わせて使うと便利！
   50%で基本表示させたいけど、◯◯px以上にはしたくない！など
  - max-width:100%により画面サイズから画像がはみ出ないように設定できる
  - 縦横比が崩れてしまったときはheight: autoを指定

- links [【CSS】max-widthとmin-widthの使い方まとめ](https://saruwakakun.com/html-css/basic/max-min-width)

### Day 67: 2020/07/13
- Today's Progress :vuex
- Thoughts :本業が忙しくなかなか時間がとれないので、Udemyをスキマ時間にみて勉強中。
- links [超Vue.js 完全パック - もう他の教材は買わなくてOK！ (Vue Router, Vuex含む)](https://www.udemy.com/course/vue-js-complete-guide/)


### Day 68: 2020/07/26
- Today's Progress :vue emit
- Thoughts :dialogをcomponent化したらうまくダイアログ開閉ができくなったのだけどvue emitで解消できた！
- links [超Vue.js 完全パック - もう他の教材は買わなくてOK！ (Vue Router, Vuex含む)](https://www.udemy.com/course/vue-js-complete-guide/)


### Day 69: 2020/07/27
- Today's Progress :vue directory
- Thoughts :こちらのページを参考にvue directoryを適正化してスッキリした！
- links [Vue.js ディレクトリ構成 色々試してみた](https://qiita.com/tockn/items/2ce68b99e0839df52200)

### Day 70: 2020/07/29
- Today's Progress :vue props
- Thoughts :propsでデータを渡すときにdialogとprops&emitの組み合わせでやりかたに悩む。dialogのcloseイベントをうまく取得できていないことが問題。

### Day 71: 2020/08/02
- Today's Progress :vuetify
- Thoughts :vuetifyでボタンの中央寄せができずトライ＆エラー。vuetifyの基本から再度勉強し直し中。

### Day 72: 2020/08/08
- Today's Progress :vue 動的class
- Thoughts :vueで動的にclass名を変更してcssを適用させて、ボタンの見た目を動的に変更することが割と簡単にできてよかった！
- links [クラスとスタイルのバインディング](https://jp.vuejs.org/v2/guide/class-and-style.html)

### Day 73: 2020/08/09
- Today's Progress :vuex mutations
- Thoughts :mutationでpayloadにオブジェクトを引数として更新をかけたいときにエラーになり少しハマった。オブジェクトのkeyを設定してmutaionを呼び出すことで解決できた
```
        this.setDisplayPlayItem({ response: response });
```
- links [vuex mutation](https://vuex.vuejs.org/ja/guide/mutations.html)

### Day 74: 2020/08/12
- Today's Progress :vuex mutations
- Thoughts :vuex mutationにオブジェクトを渡したときにうまく値が追加できなくて少し悩んだ。デバッグでどういった値がはいってきているのかを調べて解決できた。オブジェクトと配列の取り扱いの理解が浅いことがよくないな。
- links [vuex mutation](https://vuex.vuejs.org/ja/guide/mutations.html)

### Day 75: 2020/08/13
- Today's Progress :vue youtube
- Thoughts :vueにyoutubeの埋め込み。youtube埋め込みをしたときに表示サイズがうまくできなかったがprops指定を変えて対応できた
- links [vue-youtube](https://github.com/anteriovieira/vue-youtube#readme)

### Day 76: 2020/08/19
- Today's Progress :heroku deploy
- Thoughts :herokuにdeployしたときに画面が真っ白になるエラーが発生。いろいろ調べて原因はhttp通信をしようとしてエラー担っていることが判明。laravelの設定を変更してうまくいった。
- links [Laravel5.7: Herokuにデプロイする - Qiita](https://qiita.com/sutara79/items/a173b969474d9f5afe1b)


### Day 77: 2020/08/23
- Today's Progress :app design
- Thoughts :子供向けのアプリなので元気な色合いでデザインを調整。vuetifyでうまく調整できないところの対応が地味に面倒
- links [Asobiy](https://asobiy.herokuapp.com/)

### Day 78: 2020/08/28
- Today's Progress :app design
- Thoughts :vuetifyの指定方法がわからない箇所はcssで微調整。vuetifyの利用方針決めておかないと混乱する…
- links [Asobiy](https://asobiy.herokuapp.com/)

### Day 79: 2020/09/06
- Today's Progress :laravel検索クエリ
- Thoughts :複数条件の検索クエリが想定通り動かず調べていたら、フロント側の検索設定引数の問題だった。解決してよかった
→作成中アプリ [Asobiy](https://asobiy.herokuapp.com/)

### Day 80: 2020/09/11
- Today's Progress :Vue transition
- Thoughts :transition listを適用したらレイアウトのが崩れてしまい、cssで調整。
→作成中アプリ [Asobiy](https://asobiy.herokuapp.com/)

### Day 81: 2020/09/12
- Today's Progress :Vue&laravel
- Thoughts :laravel seederを利用してcsvデータをtableにinsertを実施。laravelほんと便利
→作成中アプリ [Asobiy](https://asobiy.herokuapp.com/)