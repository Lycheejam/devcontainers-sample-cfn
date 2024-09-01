# CloudFormation development environment on Devcontainers Sample

今までローカル環境でvenvを使って環境を分離していたものをDockerコンテナに分離します。  
ここで言う開発環境とはCFnのlinterを含んだコーディング環境を指します。素のCFnをAWS CLIで実行することを前提としています。

## NOTE

* Pythonのバージョンも変えられるようにしたかったのでryeを採用したが、コンテナイメージでPythonのバージョンは固定できるのでPoetryでも良かった。
    * バージョンハッシュでインストールバージョンをロックしてくれれば何でも良かった。
    * ryeの場合、`requirements.lock`と`requirements-dev.lock`をGtihubのDependabotが対応してないのでPoetryのほうが良いかも。
* プロダクト、チーム内にPythonベースのツールが複数あり、Pythonを複数バージョン管理しないといけないが、そこら辺に不慣れなメンバーで構成されており、度々インストールエラーが発生するみたいな状況にめちゃくちゃ良い。
    * 塩漬けリポジトリの開発環境を維持するのにもちょうど良い。

## Link

* [Developing inside a Container using Visual Studio Code Remote Development](https://code.visualstudio.com/docs/devcontainers/containers)
* [Dev Container metadata reference](https://containers.dev/implementors/json_reference/)
