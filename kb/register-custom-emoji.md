---
title: カスタム絵文字を登録する
nav_order: 5.2
parent: ナレッジベース
---

# カスタム絵文字を登録する
{: .fs-9 }

カスタム絵文字は、以下のいずれかの方法で登録できます。

## ひとつずつ登録する

カスタム絵文字の画像ファイルは登録したユーザのドライブに格納されるため、ドライブにあるカスタム絵文字の画像ファイルを削除すると、カスタム絵文字の参照ができなくなります。ドライブのフォルダ機能を使って誤操作からある程度保護するか、モデレータ権限を有するユーザにカスタム絵文字登録を申請することをおすすめします。

1. カスタム絵文字に登録する画像ファイルを準備する

1. サーバアイコンを押下し、「ツール」→「カスタム絵文字の管理」を押下する<br>
![](/assets/images/kb/register-custom-emoji-001.png)

1. 画面右上の「+」（絵文字を追加）を押下する<br>
![](/assets/images/kb/register-custom-emoji-002.png)

1. 「ファイルを選択」を押下し、「アップロード」を押下する<br>
![](/assets/images/kb/register-custom-emoji-003.png)

1. カスタム絵文字に登録する画像ファイルを選択する

1. サムネイル左側の「・・・」を押下し、「圧縮: 中」→「なし」を押下する<br>
![](/assets/images/kb/register-custom-emoji-004.png)

1. 「名前を変更」を押下する<br>
![](/assets/images/kb/register-custom-emoji-005.png)

1. カスタム絵文字情報の名前と同じ文字列と拡張子を入力し、「OK」を押下する<br>
![](/assets/images/kb/register-custom-emoji-006.png)

1. 「アップロード」を押下する<br>
![](/assets/images/kb/register-custom-emoji-007.png)

1. 「名前」、「カテゴリ」、「タグ」、「ライセンス」、「センシティブ」、「ローカルのみ」を適切に設定し、「作成」を押下する<br>
![](/assets/images/kb/register-custom-emoji-008.png)

## まとめて登録する

複数のカスタム絵文字を登録する場合は、こちらがおすすめです。

なお、カスタム絵文字の画像ファイルはシステムユーザに格納されるため、ドライブにアップロードしたカスタム絵文字用のZIPファイルを削除しても問題ありません。

1. カスタム絵文字に登録する画像ファイルと`meta.json`ファイルを準備する

1. ファイルをすべて選択して、「圧縮」などと書かれている項目を押下する<br>
![](/assets/images/kb/register-custom-emoji-009.png)

1. ZIP形式で圧縮する<br>
![](/assets/images/kb/register-custom-emoji-010.png)

1. サーバアイコンを押下し、「ツール」→「カスタム絵文字の管理」を押下する<br>
![](/assets/images/kb/register-custom-emoji-001.png)

1. 画面右上の「・・・」（もっと！）を押下する<br>
![](/assets/images/kb/register-custom-emoji-011.png)

1. 「インポート」を押下する<br>
![](/assets/images/kb/register-custom-emoji-012.png)

1. 「アップロード」を押下する<br>
![](/assets/images/kb/register-custom-emoji-013.png)

1. ZIPファイルを選択する

1. 「アップロード」を押下する<br>
![](/assets/images/kb/register-custom-emoji-014.png)

1. 「わかった」を押下する<br>
![](/assets/images/kb/register-custom-emoji-015.png)

### meta.jsonファイル記述例

JSONフォーマットで記述します。

`emojis`配列は`downloaded`真偽値、`fileName`文字列、`emoji`オブジェクトで構成されます。`downloaded`真偽値は常に`true`にし、`fileName`文字列はファイル名にする必要があります。

`emoji`オブジェクトは以下で構成されます。

- `name`文字列: 名前
- `category`文字列: カテゴリ
- `aliases`配列: タグ
- `license`文字列: ライセンス
- `isSensitive`真偽値: センシティブ
- `localOnly`真偽値: ローカルのみ

```json
{
    "emojis": [
        {
            "downloaded": true,
            "fileName": "gabbaskey_light.png",
            "emoji": {
                "name": "gabbaskey_light",
                "category": "ロゴ",
                "aliases": [
                    "がばすきー",
                    "らいとてーま",
                    "ろご"
                ],
                "license": "CC BY-NC-ND 4.0 / @aurorancer@misskey.io [利用規約](https://misskey.io/@aurorancer/pages/emoji-license)",
                "isSensitive": false,
                "localOnly": false
            }
        },
        {
            "downloaded": true,
            "fileName": "gabbaskey_dark.png",
            "emoji": {
                "name": "gabbaskey_dark",
                "category": "ロゴ",
                "aliases": [
                    "がばすきー",
                    "だーくてーま",
                    "ろご"
                ],
                "license": "CC BY-NC-ND 4.0 / @aurorancer@misskey.io [利用規約](https://misskey.io/@aurorancer/pages/emoji-license)",
                "isSensitive": false,
                "localOnly": false
            }
        }
    ]
}
```
