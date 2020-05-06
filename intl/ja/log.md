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

  - api で get するときの URL の最初に/をつける

  ```php
    axios
      .get(`/api/bookables/${this.$route.params.id}`)
      .then(response => (this.bookable = response.data));
  ```

  - gitignore が反映されなくてキャッシュが残っていることが問題だった(https://qiita.com/fuwamaki/items/3ed021163e50beab7154)

- リンク [Udemy Master Laravel 6 with Vue.js Fullstack Development](https://www.udemy.com/course/master-laravel-6-with-vuejs-fullstack-development/)
