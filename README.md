# OCR Auto Typer — C# Edition

**Windows向けOCR自動入力アプリ / OCR-based automatic typing application for Windows**

[日本語](#日本語) | [English](#english)

> [!IMPORTANT]
> **Installer-only distribution / インストーラーのみ配布**  
> This repository distributes the compiled Windows installer. **The C# source code and build scripts are not published here.**  
> このリポジトリではWindows用インストーラーを配布します。**C#のソースコードやビルド用スクリプトは公開していません。**

> [!WARNING]
> **The official Sushi-Da website prohibits improper automated typing using external tools and testing outside ordinary typing practice.** This software is unofficial and is not affiliated with Sushi-Da or Neutral. Use it **only on applications or pages you are authorized to automate**. Educational purpose, public distribution, and an MIT license do not override a third party's terms.  
> **寿司打公式サイトでは、外部ツールによる不正なタイピングやタイピング練習以外のテスト・実験は禁止されています。** 本アプリは非公式・非提携です。**自分が自動操作する許可を得ているアプリやテストページでのみ**使用してください。学習目的、一般公開、MITライセンスによって第三者の利用条件が解除されることはありません。  
> [公式の利用条件 / Official rules](https://keyx0.net/about.html)

---

## 日本語

### 概要

**OCR Auto Typer — C# Edition v1.1.0** は、画面の選択範囲に表示されたローマ字をTesseract OCRで読み取り、Windowsのキーボード入力を自動で送信するアプリです。C# / .NET 8 / Windows Formsを使用しています。

**主な機能**

- マウスでOCRの認識範囲を指定
- 認識した文字の確認
- 自動入力の開始・停止
- 安定・高速・超高速の3段階の速度切替
- `!`、`?` や末尾の `i` に対する入力・認識補助
- OCRエラーが5回続いた場合の自動停止
- 専用アイコン、スタートメニュー登録、アンインストール対応

### ダウンロードとインストール

1. このリポジトリの **Releases** を開きます。
2. バージョン **v1.1.0** のリリースが公開されていれば、**Assets** から `OCR-Auto-Typer-Setup-1.1.0.exe` をダウンロードします。
3. ダウンロードした `.exe` をダブルクリックし、セットアップ画面に従ってインストールします。
4. スタートメニューから **OCR Auto Typer** を起動します。必要に応じてデスクトップショートカットも作成できます。

> **注：** Releasesにインストーラーが掲載されるまでは、アプリをダウンロードできません。GitHubの **Code → Download ZIP** はREADMEとライセンス等を取得する機能であり、インストーラーのダウンロードではありません。

**動作環境：** Windows 10 / 11（64bit、主にWindows 11で動作確認）。配布用Setup.exeは.NETランタイムおよびTesseract OCRを同梱する設計のため、正しく作成されたインストーラーでは利用者がPython、.NET SDK、Tesseractを個別に導入する必要はありません。ただし、別PCでの動作はすべて保証されません。

### 操作方法

1. **自分が自動操作する許可を持つ**テスト画面を開き、ローマ字を1行で表示します。
2. **F6** で読み取る文字列の範囲をドラッグして指定します。
3. **F7** で文字認識結果を確認できます。
4. 入力先の画面をクリックしてから **F8** で開始します。
5. **F9** で停止し、**F10** で入力速度を切り替えます。

| キー | 動作 |
| --- | --- |
| `F6` | OCRの認識範囲を選択 |
| `F7` | OCR結果を確認（プレビュー画像保存） |
| `F8` | 自動入力開始・再開 |
| `F9` | 自動入力停止 |
| `F10` | 速度切替（高速 → 超高速 → 安定） |
| `Ctrl + Shift + Q` | アプリ終了 |
| マウスを画面左上へ移動 | 緊急停止 |

入力は**現在フォーカスされているウィンドウ**に送られます。パスワード欄、チャット、業務アプリなどへの誤送信に注意してください。

### アンインストール

Windowsの **設定 → アプリ → インストールされているアプリ → OCR Auto Typer → アンインストール** から削除できます。

### よくある問題

| 症状 | 確認事項 |
| --- | --- |
| ローマ字が認識されない | F6で1行だけを指定し直し、F7で結果を確認 |
| キー入力されない | 入力先のウィンドウをクリックし、IMEを半角英数に変更 |
| 入力が抜ける | F10で「安定」に切り替えて確認 |
| OCRエラーが5回続く | 停止後に認識範囲やTesseract関連のエラー表示を確認 |
| インストーラーにWindowsの警告が出る | 配布元とファイルを確認し、不明なファイルなら実行しない。未署名のアプリでは警告が出ることがあります |

### ライセンスと注意事項

この**オリジナルアプリ**には [MIT License](LICENSE) を適用しています。日本語参考訳は [LICENSE.ja.md](LICENSE.ja.md) です。**MITライセンスはソースコードの公開を義務付けるものではありません。** このリポジトリでは配布用インストーラーのみ公開し、ソースコードは提供していません。

インストーラーには第三者製の **Tesseract OCR（Apache License 2.0）** と、別のライセンスが適用される可能性がある依存DLLが含まれます。これらは本アプリのMITライセンスの対象外です。配布者は**実際に同梱した各コンポーネントのライセンス、著作権表示および必要な通知文書を確認・添付**する必要があります。

本アプリの動作、OCR精度、入力成功率を保証するものではありません。F7等で保存される画面画像に個人情報が含まれないよう注意してください。

---

## English

### Overview

**OCR Auto Typer — C# Edition v1.1.0** is a Windows application written in C# / .NET 8 / Windows Forms. It uses Tesseract OCR to recognize Roman text in a selected screen area and sends simulated keystrokes to the focused application.

**Features**

- Select a screen region for OCR with the mouse
- Preview recognized text
- Start and stop automatic typing
- Three speed presets: Stable, Fast, Ultra-fast
- Handling for `!`, `?`, and missed trailing `i`
- Stop automatically after five consecutive OCR errors
- Custom icon, Start Menu shortcut, and uninstaller

### Download and install

1. Open **Releases** on this GitHub repository.
2. If **v1.1.0** has been published, download `OCR-Auto-Typer-Setup-1.1.0.exe` under **Assets**.
3. Run the `.exe` and follow the installation wizard.
4. Launch **OCR Auto Typer** from the Windows Start Menu. A desktop shortcut can optionally be created during installation.

> **Note:** The application cannot be downloaded until the installer is actually uploaded to Releases. **Code → Download ZIP** downloads repository files such as README and license notices, **not** the installer.

**System requirements:** Windows 10 / 11 (64-bit; mainly tested on Windows 11). The installer build is designed to bundle the .NET runtime and Tesseract OCR, so users should not need to separately install Python, the .NET SDK, or Tesseract when the installer has been packaged correctly. Compatibility with all Windows PCs is not guaranteed.

### Usage

1. Open a text page or application **you have permission to automate**, displaying a single line of Roman characters.
2. Press **F6** and drag to select the text region.
3. Press **F7** to verify the OCR result if needed.
4. Focus the intended input target and press **F8** to start.
5. Press **F9** to stop, or **F10** to change speed.

| Key | Action |
| --- | --- |
| `F6` | Select OCR region |
| `F7` | Preview OCR output (save preview image) |
| `F8` | Start / resume |
| `F9` | Stop |
| `F10` | Cycle speed presets (Fast → Ultra-fast → Stable) |
| `Ctrl + Shift + Q` | Exit |
| Move mouse to upper-left corner | Emergency stop |

Keystrokes go to the **currently focused window**. Avoid accidental typing into passwords, chats, or work applications.

### Uninstall

Go to **Windows Settings → Apps → Installed apps → OCR Auto Typer → Uninstall**.

### Troubleshooting

| Issue | What to check |
| --- | --- |
| OCR cannot recognize text | Select a single line again with F6; inspect with F7 |
| No keystrokes arrive | Focus the intended window and switch IME to English / half-width input |
| Missed keys | Try Stable speed using F10 |
| Five OCR failures | Inspect the error message and OCR region, then retry |
| Windows warns about the setup executable | Verify the publisher and downloaded file. Unsigned apps may trigger warnings; do not run untrusted files |

### License, restrictions, and disclaimer

The **original application** is licensed under the [MIT License](LICENSE); see the [Japanese reference translation](LICENSE.ja.md). **MIT does not require publishing source code.** This is a **binary installer-only distribution**; C# source files and build scripts are not provided in this repository.

The installer also includes **Tesseract OCR (Apache License 2.0)** and may contain third-party DLLs under other licenses. They are **not** relicensed under this project's MIT License. The distributor must review the **actual bundled components** and provide the required third-party license texts, notices, and attributions.

This software is supplied **as is**, without guarantees of compatibility, OCR accuracy, or successful input. Debug OCR screenshots may contain private information. The official Sushi-Da website prohibits improper automated typing and testing outside ordinary typing practice; see its [usage rules](https://keyx0.net/about.html). This is an independent, unofficial project and does not grant any permission to automate third-party services.
