# セットアップ手順

**上から順に、飛ばさずに進めてください。**
各ステップの最後に「確認」があります。そこが合っていなければ、次に進まないこと。

Windows / Git Bash を前提にしています。

---

## 0　作業フォルダの場所

この講座では、次の場所で作業します。

```
C:\Users\<自分のユーザー名>\shibalab\
```

`<自分のユーザー名>` は人によって違います。エクスプローラーのアドレス欄に
`%USERPROFILE%` と入力して Enter を押すと、その場所が開きます。

> **デスクトップに置かないでください。**
> OneDrive を使っていると、デスクトップの本当の場所が
> `C:\Users\<名前>\OneDrive\デスクトップ` にずれていることがあり、
> 2日目に git がフォルダを見つけられなくなります。

**まず `shibalab` という名前のフォルダを作ります。**

1. エクスプローラーのアドレス欄に `%USERPROFILE%` と入れて Enter
2. 右クリック → 新規作成 → フォルダー
3. 名前を `shibalab` にする

**確認**　アドレス欄が `C:\Users\<自分の名前>\shibalab` になっている

---

## 1　教材をダウンロードする

次のリンクを開くと、zip ファイルのダウンロードが始まります。
**GitHub のアカウントは不要です。**

<https://github.com/uni-bit/shibalab-tilt-maze/archive/refs/heads/main.zip>

**確認**　`ダウンロード` フォルダに `shibalab-tilt-maze-main.zip`（約 170KB）がある

---

## 2　展開する

**zip を開いたまま中のファイルを編集しないでください。**
編集して保存したつもりでも、一時フォルダに書かれて消えます。**必ず展開します。**

1. `shibalab-tilt-maze-main.zip` を右クリック
2. **「すべて展開」** を選ぶ
3. 展開先の欄を消して、`C:\Users\<自分の名前>\shibalab` と入力する
4. 「展開」を押す

展開できたら、**フォルダの名前を `tilt-maze` に変えます**（右クリック → 名前の変更）。

### 確認

こうなっていれば正解です。

```
C:\Users\<自分の名前>\shibalab\
└── tilt-maze\
    ├── index.html        ← 自分で書く
    ├── style.css         ← 自分で書く
    ├── game.js           ← 自分で書く
    ├── engine.js         ← 触らない
    ├── three.min.js      ← 触らない
    ├── sensor-check.html
    ├── README.md
    └── docs\
        ├── setup.md      ← この文書
        └── session3.md
```

**`index.html` が `tilt-maze` の直下にあること。** ここが一番間違えやすい箇所です。

もし `tilt-maze` を開いて、中にまた `shibalab-tilt-maze-main` というフォルダがあり、
その中に `index.html` が入っていたら、**フォルダが二重になっています。**
内側のフォルダの中身を全部選んで、一つ上の階層に移動してください。

---

## 3　VSCode で開く

1. VSCode を起動する
2. メニューの **ファイル → フォルダーを開く**
3. `C:\Users\<自分の名前>\shibalab\tilt-maze` を選ぶ

> **「ファイルを開く」ではなく「フォルダーを開く」です。**
> ファイル単体で開くと、他のファイルが見えず作業しづらくなります。

**確認**　VSCode の左側に `INDEX.HTML` `STYLE.CSS` `GAME.JS` などが一覧で並んでいる

---

## 4　画面で確認する方法

`index.html` を**ダブルクリック**すると、ブラウザで開きます。それだけです。
サーバーを立てる必要はありません。

編集して保存したら、ブラウザで **F5**（再読み込み）を押すと反映されます。

> 見た目が変わらないときは **Ctrl + Shift + R**（キャッシュを無視して再読み込み）。

**確認**　まだ何も書いていないので、真っ白なページが開く。それで正しい

---

## 5　GitHub のアカウントを作る

<https://github.com/signup>

- **メールアドレス** … 認証コードが届くので、その場で見られるものにする
- **ユーザー名** … 先着順。取られていたら候補を変える。後で URL に使われる
- **パスワード** … 忘れないこと

**確認**　GitHub にログインした状態で、右上に自分のアイコンが出ている

---

## 6　自分のリポジトリを作る

1. <https://github.com/uni-bit/shibalab-tilt-maze> を開く
2. 緑の **「Use this template」** → **「Create a new repository」**
3. **Repository name** … `tilt-maze`（好きな名前でよい）
4. **Public** のままにする（Private だと公開できません）
5. **「Create repository」**

**確認**　`https://github.com/<自分のユーザー名>/tilt-maze` が開き、
ファイルが一覧に並んでいる

---

## 7　公開する設定（GitHub Pages）

1. 自分のリポジトリの **Settings**（上の方のタブ）
2. 左のメニューから **Pages**
3. **Source** を `Deploy from a branch`
4. **Branch** を `main`、フォルダは `/ (root)`
5. **Save**

1分ほど待つと、ページの上の方に公開 URL が出ます。

```
https://<自分のユーザー名>.github.io/tilt-maze/
```

**確認**　その URL をスマホで開ける。まだ中身は空なので真っ白でよい

**この URL は3日間ずっと使います。** スマホのブックマークに入れておくこと。

---

## 8　1日目の公開のしかた（git は使いません）

編集した `index.html` と `style.css` を GitHub に送ります。

1. 自分のリポジトリを開く
2. **Add file** → **Upload files**
3. VSCode で編集したファイルを、ブラウザの画面にドラッグして落とす
4. 下の **Commit changes** を押す

1分ほど待ってから、自分の公開 URL をスマホで開くと反映されています。

> 送るのは**自分が編集したファイルだけ**でかまいません。
> `engine.js` と `three.min.js` は最初から入っているので、触れなくてよいです。

---

## 9　2日目：git を使う

毎回ドラッグするのをやめて、コマンドで送れるようにします。

### 9-1　名前を登録する（最初の1回だけ）

Git Bash を開いて、次の2行を実行します。

```bash
git config --global user.name "自分のGitHubユーザー名"
git config --global user.email "GitHubに登録したメールアドレス"
```

**確認**　次を実行して、入力した内容が表示される

```bash
git config --global user.name
```

### 9-2　自分のリポジトリを手元に持ってくる

```bash
cd ~/shibalab
git clone https://github.com/<自分のユーザー名>/tilt-maze.git
```

> `~` は `C:\Users\<自分の名前>` のことです。
> `cd` は「そのフォルダへ移動する」という意味です。

初回は**ブラウザが開いて GitHub の認証画面**が出ます。
**Authorize**（許可）を押してください。
開いていないように見えるときは、他のウィンドウの後ろに隠れていないか確認します。

**確認**　`C:\Users\<自分の名前>\shibalab\` の中に、
1日目の `tilt-maze` とは別に、新しいフォルダができている

```
C:\Users\<自分の名前>\shibalab\
├── tilt-maze\        ← 1日目に使ったもの。もう使わないが消さない
└── tilt-maze\        ← clone したもの。★2日目からはこちらで作業する
```

> 同じ名前になって紛らわしい場合は、1日目のフォルダの名前を
> `tilt-maze-day1` に変えてから clone してください。

### 9-3　VSCode で開き直す

**ファイル → フォルダーを開く** で、**clone した方**のフォルダを開きます。
2日目以降はこちらで作業します。

### 9-4　変更を送る

```bash
cd ~/shibalab/tilt-maze
git add .
git commit -m "何を変えたかを書く"
git push
```

**確認**　1分ほど待って、自分の公開 URL に反映されている

---

## うまくいかないとき

### 編集したのに、ブラウザで変わらない

- 保存したか（**Ctrl + S**）
- **Ctrl + Shift + R** で再読み込み
- **zip の中のファイルを編集していないか**（手順 2 に戻る）

### `git commit` で `Please tell me who you are` と出る

手順 9-1 をやっていません。

### `git push` でユーザー名とパスワードを聞かれる

そこに GitHub のパスワードを入れても**必ず失敗します**。
次を実行して `manager` と表示されるか確認してください。

```bash
git config credential.helper
```

何も出ない場合は講師に申告してください。Git の入れ直しが必要です。

### `cd ~/shibalab` で `No such file or directory` と出る

手順 0 のフォルダが作れていないか、場所が違います。
次で今いる場所を確認できます。

```bash
pwd
ls
```

### 公開 URL が 404 になる

- 手順 7 の設定を保存したか
- リポジトリが **Public** になっているか
- 保存から1〜2分待ったか
