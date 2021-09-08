# bizrobo-tips
sample robots, tips and so forth for helping your daily mundane tasks well.

## Contents
- [usingBabel](./usingBabel/Library)　… DS のデフォルトブラウザで ES6 を処理する手順

## 命名規則

### フォルダ構成

@付きは任意の文字列フォルダ
```cmd
/@ProjectName
    /Library
        /robots
            - JobARobo.robot
            /@JobBRobo
                - JobBMain.robot
                - JobBPrint.robot
        /snippets
            - LogIn.snippet
            - ReportError.snippet
        /types
            - Credential.type
            - Book.type
```

### ファイルレベル
|  ケース  |  規則  |例|
| ---- | ---- |----|
| ロボット  | アッパーキャメルケース| WebAutomationRobot.robot|
| DAロボット | アッパーキャメルケース | DesktopAutoRobot.robot |
| スニペット| アッパーキャメルケース | Snippet.snippet |
| タイプ| アッパーキャメルケース | TypeFile.type |

### 変数タイプ
|  ケース  |  規則  |例|
| ---- | ---- |----|
| シンプルタイプ | キャメルケース | simple, simpleVal |
| コンプレックスタイプ | アッパーキャメルケース | Complex, ComplexVal |

### 属性名
|  ケース  |  規則  |例|
| ---- | ---- |----|
| 変数 | キャメルケース | Complex.attribute |
| 定数 | 大文字＋スネークケース | Complex.FIXED_VALUE |
