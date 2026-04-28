# PHP Use Helper

**PHP Use Helper** makes it effortless to manage `use` statements in your PHP files.  
No more typing long namespaces by hand — just pick from the list and it's done.

Built with **Symfony** and **Doctrine** developers in mind.

---

## Features

### Add a `use` statement — `Cmd+Shift+U` / `Ctrl+Shift+U`

Place your cursor on a class name and press the shortcut, or right-click and choose **PHP: Add use statement** from the context menu.  
A quick-pick list appears, automatically filtered by the word under your cursor.  
Select a class and the `use` statement is inserted at the correct position in your file.

### Sort `use` statements — `Cmd+Shift+S` / `Ctrl+Shift+S`

Sorts all `use` statements in the file alphabetically in one step.  
Also available via right-click → **PHP: Sort use statements**.

### Remove unused `use` statements — right-click menu

Right-click anywhere in the editor → **PHP: Remove unused use statements**.  
The extension detects which classes are not referenced in the file and removes them after confirmation.

### Hover to see the full class name

Hover over any class name in your file to see its fully qualified namespace in a tooltip.

---

## Keyboard Shortcuts

| Action | Mac | Windows / Linux |
|---|---|---|
| Add use statement | `Cmd+Shift+U` | `Ctrl+Shift+U` |
| Sort use statements | `Cmd+Shift+S` | `Ctrl+Shift+S` |

---

## Right-click Context Menu

All three commands are available from the editor context menu when editing a PHP file:

- **PHP: Add use statement**
- **PHP: Sort use statements**
- **PHP: Remove unused use statements**

Right-click anywhere inside a `.php` file to access these commands instantly, without needing to remember any keyboard shortcuts.

---

## Supported Classes

The extension includes presets for the most commonly used classes in Symfony and Doctrine projects.

**Symfony**
- Controller, Request, Response, JsonResponse, RedirectResponse
- Route (Attribute & Annotation)
- AbstractType, FormBuilderInterface, OptionsResolver
- TextType, EmailType, PasswordType, IntegerType, DateTimeType, SubmitType, ChoiceType, TextareaType
- ValidatorInterface, NotBlank, Length, Email
- UserInterface, PasswordAuthenticatedUserInterface, UserPasswordHasherInterface
- SerializerInterface, EventSubscriberInterface

**Doctrine ORM**
- EntityManagerInterface, EntityRepository, ServiceEntityRepository
- ManagerRegistry, Paginator
- Mapping: Entity, Column, Id, GeneratedValue, ManyToOne, OneToMany, ManyToMany, JoinColumn, Table

**PHP Standard**
- DateTime, DateTimeImmutable, DateTimeInterface
- Exception, RuntimeException, InvalidArgumentException, LogicException

---

## Adding Your Own Classes

Open `src/extension.js` and add entries to the `COMMON_CLASSES` array:

```js
const COMMON_CLASSES = [
  // Add your own classes here
  'App\\Service\\MyCustomService',
  'App\\Repository\\MyRepository',
  ...
];
```

---

## Installation

### From VS Code Marketplace

Search for **"PHP Use Helper"** in the Extensions panel, or install via Quick Open:

```
Ctrl+P → ext install colscenery.php-use-helper
```

### From VSIX file

```bash
code --install-extension php-use-helper-1.0.2.vsix
```

Or open VSCode → `Cmd+Shift+P` → `Extensions: Install from VSIX...`

---

## Requirements

- VSCode `^1.85.0`
- A PHP project (Symfony recommended)

---

## Changelog

### 1.0.2
- Updated extension icon

### 1.0.1
- Initial public release

---

## License

MIT
