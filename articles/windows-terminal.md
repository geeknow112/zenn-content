---
title: "Windows Terminalとは？初心者エンジニア向け設定ガイド"
emoji: "💻"
type: "tech"
topics: ["Windows Terminal", "ターミナル", "初心者向け"]
published: true
---

こんにちは。今回は、Windows Terminalについて初心者エンジニア向けて、解説していきます。

## はじめに

Windows Terminalは、Windows用のオープンソースのターミナルエミュレータです。Windows 10バージョン1903以降で利用可能で、コマンドプロンプト、PowerShell、WSL(Windows Subsystem for Linux)などのシェルを同時に利用できます。

Windows Terminalは、使いやすくカスタマイズ性が高いため、多くの開発者やエンジニアに利用されています。本記事では、Windows Terminalの基本的な使い方や設定方法を紹介します。

## Windows Terminalの基本的な使い方

Windows Terminalを開くには、スタートメニューから「Windows Terminal」を検索して起動します。

Windows Terminalでは、複数のタブを開いて異なるシェルを同時に利用できます。新しいタブを開くには、`Ctrl + Shift + T`を押します。また、現在のタブを複製して新しいタブを開くには、`Ctrl + Shift + D`を押します。

Windows Terminalには、デフォルトで以下のシェルが設定されています。

- コマンドプロンプト
- PowerShell
- Azure Cloud Shell

これらのシェルを切り替えるには、`Ctrl + Shift + 1`〜`3`を押します。また、利用可能なすべてのシェルを一覧で表示するには、`Ctrl + Shift + Space`を押します。

## Windows Terminalのカスタマイズ

Windows Terminalは、カスタマイズ性が非常に高いため、自分好みのターミナル環境を構築できます。カスタマイズには、以下のような方法があります。

### プロファイルの編集

Windows Terminalでは、各シェルごとにプロファイルが設定されています。プロファイルは、シェルの起動時に適用される設定を定義するものです。

プロファイルは、`settings.json`というファイルで管理されています。このファイルを編集することで、プロファイルの設定を変更できます。

以下は、プロファイルの例です。

```json
{
    "guid": "{00000000-0000-0000-ba54-000000000001}",
    "name": "Command Prompt",
    "commandline": "cmd.exe",
    "icon": "ms-appx:///ProfileIcons/{0caa0dad-35be-5f56-a8ff-afceeeaa6101}.png",
    "hidden": false
}
```

- `guid`: プロファイルの一意なID。自動生成されます。
- `name`: プロファイルの名前。
- `commandline`: 起動するシェルのコマンドライン。
- `icon`: プロファイルのアイコン。
- `hidden`: プロファイルを非表示にするかどうか。

### カラースキームの変更

Windows Terminalでは、テキストの色や背景色を変更することができます。カラースキームは、`settings.json`で定義されています。

以下は、カラースキームの例です。

```json
"schemes": [
    {
        "name": "My Color Scheme",
        "background": "#0C0C0C",
        "black": "#0C0C0C",
        "blue": "#003"
    }
]
```

:::message alert
Windows Terminalの設定ファイルである`settings.json`を変更する際は、誤った設定値を入力しないように注意してください。誤った設定値を入力すると、Windows Terminalが正常に動作しなくなる場合があります。
:::

### キーバインドの変更

Windows Terminalでは、キーバインドを変更することができます。キーバインドは、`settings.json`で定義されています。

以下は、キーバインドの例です。

```json
"keybindings": [
    {
        "command": "copy",
        "keys": "ctrl+c"
    },
    {
        "command": "paste",
        "keys": "ctrl+v"
    }
]
```

- `command`: 実行するコマンド。
- `keys`: キーバインド。

### フォントの変更

Windows Terminalでは、フォントを変更することができます。フォントは、`settings.json`で定義されています。

以下は、フォントの例です。

```json
"profiles": {
    "defaults": {
        "fontFace": "Cascadia Code",
        "fontSize": 10
    }
}
```

- `fontFace`: 使用するフォントの名前。
- `fontSize`: フォントのサイズ。

## サンプルコード

### プロファイルの例

```json
{
    "guid": "{00000000-0000-0000-ba54-000000000001}",
    "name": "Command Prompt",
    "commandline": "cmd.exe",
    "icon": "ms-appx:///ProfileIcons/{0caa0dad-35be-5f56-a8ff-afceeeaa6101}.png",
    "hidden": false
}
```

### カラースキームの例

```json
"schemes": [
    {
        "name": "My Color Scheme",
        "background": "#0C0C0C",
        "black": "#0C0C0C",
        "blue": "#003F5F",
        "brightBlack": "#686868",
        "brightBlue": "#268BD2",
        "brightCyan": "#2AA198",
        "brightGreen": "#859900",
        "brightPurple": "#D33682",
        "brightRed": "#DC322F",
        "brightWhite": "#FFFFFF",
        "brightYellow": "#B58900",
        "cursorColor": "#FFFFFF",
        "cyan": "#2AA198",
        "foreground": "#FFFFFF",
        "green": "#859900",
        "purple": "#D33682",
        "red": "#DC322F",
        "white": "#B3B3B3",
        "yellow": "#B58900"
    }
]
```

## まとめ

本記事では、Windows Terminalの基本的な使い方やカスタマイズ方法について解説しました。Windows Terminalは、オープンソースであり、様々な設定が可能です。初めて使用する人でも、この記事を参考にして自分好みのターミナル環境を構築してみてください。

参考記事：
https://www.kimoton.com/entry/20201011/1602424175
- [Windows Terminal Documentation](https://docs.microsoft.com/en-us/windows/terminal/)
- [Windows Terminal Tips and Tricks](https://devblogs.microsoft.com/commandline/windows-terminal-tips-and-tricks/)
