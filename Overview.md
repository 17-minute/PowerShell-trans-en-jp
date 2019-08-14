原文は[こちら](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-6)

## PowerShell/PowerShell

| 原文（英語） | 訳文（日本語） |
|---|---|
|08/27/2018|08/27/2018|
|2 minutes to read|読み終わるまで2分|
|\*|\*|
|PowerShell is a task-based command-line shell and scripting language built on .NET.|PowerShellはタスクベースのコマンドラインシェルであり、.NETに基づいたスクリプト言語です。|
|PowerShell helps system administrators and power-users rapidly automate tasks that manage operating systems (Linux, macOS, and Windows) and processes.|PowerShellはシステム管理者やパワーユーザがオペレーションシステム（Linux、macOS、Windows）を管理するタスクを迅速に自動化するのに役立ちます。|
|PowerShell commands let you manage computers from the command line.|PowerShellのコマンドを使えばコマンドラインからコンピュータを管理できます。|
|PowerShell providers let you access data stores, such as the registry and certificate store, as easily as you access the file system.|PowerShellプロバイダを使えば、ファイルシステムにアクセスするのと同じくらい容易にレジストリや証明書ストアといったデータストアにアクセスすることができます。|
|PowerShell includes a rich expression parser and a fully developed scripting language.|PowerShellには豊富な式パーサと十分に開発されたスクリプト言語が備わっています。|

## PowerShell is open-source/PowerShellはオープンソース

| 原文（英語） | 訳文（日本語） |
|---|---|
|PowerShell base source code is now available in GitHub and open to community contributions.|PowerShellの基礎となるソースコードは現在GitHubで入手でき、自由にコミュニティへの貢献ができます。|
|See [PowerShell source on GitHub](https://github.com/powershell/powershell).|[GitHub上のPowerShellのソースコード](https://github.com/powershell/powershell)を参照ください。|
|You can start with the bits you need at [Get PowerShell](https://github.com/PowerShell/PowerShell#get-powershell). Or, perhaps, with a quick tour at Getting Started.|[PowerShellの入手](https://github.com/PowerShell/PowerShell#get-powershell)で手に入る少しの必要なものがあれば始めることができます。あるいは、「さあ、はじめよう」のクイックツアーで始めることもできるでしょう。|

## PowerShell design goals/PowerShellの設計目標
| 原文（英語） | 訳文（日本語） |
|---|---|
|PowerShell is designed to improve the command-line and scripting environment by eliminating long-standing problems and adding new features.|PowerShellは長きにわたる問題を解消するとともに、新機能を加えることによりコマンドラインとスクリプティング環境を改善するために設計されました。|

### Discoverability/見つけやすさ
| 原文（英語） | 訳文（日本語） |
|---|---|
|PowerShell makes it easy to discover its features. For example, to find a list of cmdlets that view and change Windows services, type:|PowerShellでは、その機能を見つけるのが簡単です。例えば、Windowsのサービスを閲覧したり変更したりするコマンドレットのリストを見つけるには次のようにタイプすればいいのです。|

```powershell
Get-Command *-Service
```

| 原文（英語） | 訳文（日本語） |
|---|---|
|After discovering which cmdlet accomplishes a task, you can learn more about the cmdlet by using the Get-Help cmdlet.|どのコマンドレットがタスクを完了させるかわかったら、Get-Helpコマンドレットでそのコマンドレットについてもっと知ることができます。|
|For example, to display help about the Get-Service cmdlet, type:|例えば、Get-Serviceコマンドレットについてのヘルプを表示するには次のようにタイプすればいいのです。|

```powershell
Get-Help Get-Service
```

| 原文（英語） | 訳文（日本語） |
|---|---|
|Most cmdlets return objects that can be manipulated and then rendered as text for display.|ほとんどのコマンドレットはオブジェクトを返します。その際、オブジェクトを変更後、表示用のテキストにレンダリングすることが可能です。|
|To fully understand the output of a cmdlet, pipe the output to the Get-Member cmdlet.|コマンドレットの出力について完全に理解するには、出力をGet-Memberコマンドレットにパイプで渡します。|
|For example, the following command displays information about the members of the object output by the Get-Service cmdlet.|例えば、次のコマンドはGet-Serviceコマンドレットからの出力オブジェクトのメンバーについての情報を表示します。|

```powershell
Get-Service | Get-Member
```

### Consistency/一貫性
| 原文（英語） | 訳文（日本語） |
|---|---|
|Managing systems can be a complex task. Tools that have a consistent interface help to control the inherent complexity.|システム管理は複雑なタスクです。一貫したインターフェースを備えたツールがあれば内在する複雑さを制御することができます。|
|Unfortunately, command-line tools and scriptable Component Object Model (COM) objects aren't known for their consistency.|不幸なことに、コマンドラインツールとスクリプト可能なコンポーネントオブジェクトモデル（COM）のオブジェクトはその一貫性で知られてはいません。|
|The consistency of PowerShell is one of its primary assets.|PowerShellの一貫性はその主な強みのひとつです。|
|For example, if you learn how to use the Sort-Object cmdlet, you can use that knowledge to sort the output of any cmdlet.|例えば、Sort-Objectコマンドレットの使い方を身につければ、どんなコマンドレットでもその出力をソートする知識を持つことにもなります。|
|You don't have to learn the different sorting routines of each cmdlet.|それぞれのコマンドレットにある異なったソート方法を身につける必要はないのです。|
|Additionally, cmdlet developers don't have to design sorting features for their cmdlets.|加えて、コマンドレットの開発者は自分たちのコマンドレットのためにソート機能を開発する必要がありません。|
|PowerShell provides a framework with the basic features that forces consistency.|PowerShellは一貫性を強化する基本的な機能を備えたフレームワークを提供しています。|
|The framework eliminates some choices that are left to the developer.|そのフレームワークは開発者に残されたいくつかの選択肢を取り除きます。|
|But, in return, it makes the development of cmdlets much simpler.|しかし、代わりに、そのおかげでコマンドレットの開発はずっとシンプルなものになります。|

### Interactive and scripting environments/対話型・スクリプティング環境
| 原文（英語） | 訳文（日本語） |
|---|---|
|The Windows Command Prompt provides an interactive shell with access to command-line tools and basic scripting.|WIndowsのコマンドプロンプトはコマンドラインツールと基本的なスクリプティングへのアクセスを伴ったインタラクティブシェルを提供しています。|
|Windows Script Host (WSH) has scriptable command-line tools and COM automation objects, but doesn't provide an interactive shell.|Windowsスクリプトホスト（WSH）はスクリプト可能なコマンドラインツールとCOM自動化オブジェクトを備えていますが、インタラクティブシェルは提供していません。|
|PowerShell combines an interactive shell and a scripting environment.|PowerShellはインタラクティブシェルとスクリプティング環境を組み合わせました。|
|PowerShell can access command-line tools, COM objects, and .NET class libraries.|PowerShellはコマンドラインツール、COMオブジェクト、そして.NETクラスライブラリにアクセスできます。|
|This combination of features extends the capabilities of the interactive user, the script writer, and the system administrator.|この機能の組み合わせによって、インタラクティブユーザ、スクリプトライター、システム管理者の能力を拡大することができるのです。|

### Object orientation/オブジェクト指向型
| 原文（英語） | 訳文（日本語） |
|---|---|
|PowerShell is based on object not text. The output of a command is an object.|PowerShellはテキストではなくオブジェクトをベースにしています。コマンドの出力はオブジェクトです。|
|You can send the output object, through the pipeline, to another command as its input.|出力オブジェクトをパイプラインを通じて別のコマンドに入力オブジェクトとして渡すことができます。|
|This pipeline provides a familiar interface for people experienced with other shells.|このパイプラインは他のシェルを使ったことのある人にとっては馴染みのあるインターフェースを提供します。|
|PowerShell extends this concept by sending objects rather than text.|PowerShellはテキストではなくオブジェクトを渡すことでこのコンセプトを拡大します。|

### Easy transition to scripting/スクリプトへの移行の容易さ
| 原文（英語） | 訳文（日本語） |
|---|---|
|PowerShell's command discoverability makes it easy to transition from typing commands interactively to creating and running scripts.|PowerShellのコマンドの見つけやすさによって、対話的なコマンドの入力からスクリプトの作成と実行への移行が簡単になります。|
|PowerShell transcripts and history make it easy to copy commands to a file for use as a script.|PowerShellのトランスクリプトと履歴を利用すればスクリプトとして使うためのファイルにコマンドをコピーするのが簡単になります。|
