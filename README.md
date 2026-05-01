# PHP Use Helper

PHP Use Helper は、Visual Studio Code で PHP の `use` 文をすばやく追加・補完・整理・削除するための拡張機能です。

長い名前空間を手入力する手間を減らし、クラス名から候補を選ぶだけで PHP ファイル上部へ `use` 文を追加できます。Symfony、Laravel、Doctrine のよく使うクラス候補に加えて、現在のワークスペース内にある独自クラスも検出します。

## 主な機能

### `use` 文の補完

PHP ファイルで `use <クラス名>` と入力すると、候補一覧にクラスが表示されます。

ワークスペース内の PHP ファイルから `class`、`interface`、`trait`、`enum` を検出し、`vendor` フォルダなどの外部依存よりも、プロジェクト内のクラスを優先して表示します。

除外対象の例:

- `vendor`
- `node_modules`
- `.git`
- `storage`
- `var/cache`

### `use` 文を追加

クラス名にカーソルを合わせて、ショートカットを押すか、右クリックメニューから **PHP: Add use statement** を実行します。

カーソル下の単語で絞り込まれた Quick Pick が表示され、選択したクラスの `use` 文が PHP ファイルの適切な位置に挿入されます。

| 操作 | Mac | Windows / Linux |
|---|---|---|
| `use` 文を追加 | `Cmd+Shift+U` | `Ctrl+Shift+U` |

### `use` 文をソート

ファイル内の `use` 文をアルファベット順に並び替えます。

| 操作 | Mac | Windows / Linux |
|---|---|---|
| `use` 文をソート | `Cmd+Shift+S` | `Ctrl+Shift+S` |

### 未使用の `use` 文を削除

右クリックメニューから **PHP: Remove unused use statements** を実行すると、ファイル内で参照されていない `use` 文を検出し、確認後に削除します。

### ホバーで完全修飾クラス名を確認

インポート済みのクラス名にホバーすると、対応する完全修飾クラス名をツールチップで確認できます。

## コマンド

PHP ファイルを編集中に、エディタの右クリックメニューまたは Command Palette から以下のコマンドを実行できます。

- **PHP: Add use statement**
- **PHP: Sort use statements**
- **PHP: Remove unused use statements**

## フレームワーク対応

### Symfony

コントローラー、HTTP Foundation、Routing、Form、Validator、Security、Serializer、EventDispatcher など、Symfony プロジェクトでよく使うクラス候補を含んでいます。

### Laravel

Laravel プロジェクトでは、プロジェクト内クラスの検出に加えて、Request、Response、Controller、Facade、Eloquent、Migration、FormRequest、Queue、Notification、Mail などのよく使うクラス候補を利用できます。

### Doctrine

EntityManager、Repository、ManagerRegistry、Paginator、Mapping 属性など、Doctrine ORM でよく使うクラス候補を含んでいます。

## 対応プリセット

### Symfony

- `AbstractController`, `Request`, `Response`, `JsonResponse`, `RedirectResponse`
- `Route`
- `AbstractType`, `FormBuilderInterface`, `OptionsResolver`
- `TextType`, `EmailType`, `PasswordType`, `IntegerType`, `DateTimeType`, `SubmitType`, `ChoiceType`, `TextareaType`
- `ValidatorInterface`, `NotBlank`, `Length`, `Email`
- `UserInterface`, `PasswordAuthenticatedUserInterface`, `UserPasswordHasherInterface`
- `SerializerInterface`, `Groups`, `EventSubscriberInterface`

### Laravel

- `Request`, `Response`, `JsonResponse`, `Controller`, `Redirector`
- `Route`, `Auth`, `Cache`, `DB`, `Gate`, `Hash`, `Log`, `Storage`, `Validator`, `View`, `Mail`, `Notification`, `Schema`
- `Collection`, `ServiceProvider`, `Str`, `Carbon`
- `Model`, `Builder`, `HasFactory`
- `Migration`, `Blueprint`
- `Command`, `ShouldQueue`, `Queueable`, `SerializesModels`, `InteractsWithQueue`
- `FormRequest`, `Rule`, `Mailable`
- `Channel`, `PrivateChannel`, `PresenceChannel`, `ShouldBroadcast`
- `HandlesAuthorization`, `Authenticate`

### Doctrine ORM

- `EntityManagerInterface`, `EntityRepository`, `ServiceEntityRepository`
- `ManagerRegistry`, `Paginator`
- `Entity`, `Column`, `Id`, `GeneratedValue`, `ManyToOne`, `OneToMany`, `ManyToMany`, `JoinColumn`, `Table`

### PHP 標準

- `DateTime`, `DateTimeImmutable`, `DateTimeInterface`
- `Exception`, `RuntimeException`, `InvalidArgumentException`, `LogicException`

## インストール

### Visual Studio Marketplace からインストール

VS Code の Quick Open を開き、以下を実行します。

```text
ext install colscenery.php-use-helper
```

Marketplace:

https://marketplace.visualstudio.com/items?itemName=colscenery.php-use-helper

### VSIX からインストール

```bash
code --install-extension php-use-helper-1.0.3.vsix
```

または、VS Code で **Extensions: Install from VSIX...** を実行し、VSIX ファイルを選択してください。

## 動作要件

- Visual Studio Code `^1.85.0`
- PHP ワークスペース

## 変更履歴

### 1.0.3

- プロジェクト内クラスの検出に対応
- `vendor` などを除外し、プロジェクト内クラスを補完候補の上位に表示
- `PHP: Add use statement` の Quick Pick にプロジェクト内クラスと Laravel 候補を表示
- Laravel のプリセット候補を追加
- README と Marketplace 用メタデータを更新

### 1.0.2

- 拡張機能アイコンを更新

### 1.0.1

- 初回パブリックリリース

## ライセンス

MIT
