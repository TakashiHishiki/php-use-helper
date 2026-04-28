# PHP Use Helper

PHPファイルの `use` 文を簡単に追加・整理・削除できる Visual Studio Code 拡張機能です。

長い名前空間を手動で入力する手間をなくし、リストから選ぶだけで完了します。
**Symfony** や **Doctrine** を使う開発者に最適化されています。

[![VS Code Marketplace](https://img.shields.io/visual-studio-marketplace/v/colscenery.php-use-helper?label=VS%20Code%20Marketplace&logo=visual-studio-code)](https://marketplace.visualstudio.com/items?itemName=colscenery.php-use-helper)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## 機能

### `use` 文を追加する — `Cmd+Shift+U` / `Ctrl+Shift+U`

クラス名にカーソルを合わせてショートカットを押すか、右クリックから **PHP: Add use statement** を選択します。
カーソル下の単語で自動フィルタリングされたクイックピックリストが表示されます。
クラスを選択すると、`use` 文がファイルの正しい位置に挿入されます。

### `use` 文をソートする — `Cmd+Shift+S` / `Ctrl+Shift+S`

ファイル内のすべての `use` 文をアルファベット順に一括ソートします。
右クリック → **PHP: Sort use statements** からも実行できます。

### 未使用の `use` 文を削除する — 右クリックメニュー

エディタ内で右クリック → **PHP: Remove unused use statements** を選択します。
ファイル内で参照されていないクラスを検出し、確認後に削除します。

### ホバーで完全クラス名を確認

ファイル内のクラス名にホバーすると、完全修飾の名前空間をツールチップで表示します。

---

## キーボードショートカット

| 操作 | Mac | Windows / Linux |
|------|-----|-----------------|
| `use` 文を追加 | `Cmd+Shift+U` | `Ctrl+Shift+U` |
| `use` 文をソート | `Cmd+Shift+S` | `Ctrl+Shift+S` |

---

## 右クリックコンテキストメニュー

PHPファイルの編集中にエディタ内で右クリックすると、以下の3つのコマンドにアクセスできます。

- **PHP: Add use statement**
- **PHP: Sort use statements**
- **PHP: Remove unused use statements**

ショートカットを覚えなくても、すぐに使えます。

---

## 対応クラス一覧

拡張機能には、SymfonyとDoctrineプロジェクトでよく使われるクラスのプリセットが含まれています。

### Symfony

- `Controller`, `Request`, `Response`, `JsonResponse`, `RedirectResponse`
- `Route`（属性・アノテーション両対応）
- `AbstractType`, `FormBuilderInterface`, `OptionsResolver`
- `TextType`, `EmailType`, `PasswordType`, `IntegerType`, `DateTimeType`, `SubmitType`, `ChoiceType`, `TextareaType`
- `ValidatorInterface`, `NotBlank`, `Length`, `Email`
- `UserInterface`, `PasswordAuthenticatedUserInterface`, `UserPasswordHasherInterface`
- `SerializerInterface`, `EventSubscriberInterface`

### Doctrine ORM

- `EntityManagerInterface`, `EntityRepository`, `ServiceEntityRepository`
- `ManagerRegistry`, `Paginator`
- マッピング: `Entity`, `Column`, `Id`, `GeneratedValue`, `ManyToOne`, `OneToMany`, `ManyToMany`, `JoinColumn`, `Table`

### PHP 標準

- `DateTime`, `DateTimeImmutable`, `DateTimeInterface`
- `Exception`, `RuntimeException`, `InvalidArgumentException`, `LogicException`

---

## 独自クラスの追加

`src/extension.js` を開き、`COMMON_CLASSES` 配列にエントリを追加してください。

```js
const COMMON_CLASSES = [
  // 独自クラスをここに追加
  'App\\Service\\MyCustomService',
  'App\\Repository\\MyRepository',
  ...
];
```

---

## インストール

### VS Code マーケットプレイスから

[拡張機能マーケットプレイス](https://marketplace.visualstudio.com/items?itemName=colscenery.php-use-helper) からインストールできます。

VS Code で `Ctrl+P`（Mac: `Cmd+P`）を開き、以下を貼り付けて Enter を押してください。

```
ext install colscenery.php-use-helper
```

### VSIX ファイルから

```bash
code --install-extension php-use-helper-1.0.2.vsix
```

または、VS Code で `Cmd+Shift+P` → `Extensions: Install from VSIX...` を選択してください。

---

## 動作要件

- VSCode `^1.85.0`
- PHPプロジェクト（Symfony推奨）

---

## 変更履歴

### 1.0.2
- 拡張機能アイコンを更新

### 1.0.1
- 初回パブリックリリース

---

## ライセンス

[MIT](LICENSE)
