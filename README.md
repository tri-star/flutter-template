# flutter_template

Flutterアプリのテンプレート用リポジトリ。
プロジェクト設定やfastlane、その他実装のひな型を定義する用途を想定。


## 環境変数、secret

変数              | 内容                                   | 例
----------------- | ------------------------------------- | ----------------
KEYCHAIN_PASSWORD | キーチェーンのパスワード(ワークフローの中で一時的に利用されるもの) | xxxxx
SLACK_URL | Slackの連携用URL | https://hooks.slack.com/services/xxx
FIREBASE_TOKEN | firebase login:ci で取得するトークン | 1//0envxxxxxxx
FIREBASE_APP_ID | Firebase のアプリID | 1:1004:xxxx:ios:xxxxxx
FASTLANE_USERNAME | Apple Developer ProgramのユーザーID | xxx@example.com
FASTLANE_PASSWORD | Apple Developer Programのパスワード(証明書作成時に必要) | xxxxx
FASTLANE_SESSION | fastlane spaceauth で発行したトークン | ---\n- !ruby/object:HTTP::Cookie
MATCH_PASSWORD | matchが発行した証明書を暗号化するパスワード | xxxx
MATCH_GIT_BASIC_AUTHORIZATION | %GitHubのユーザーID%:%GitHubのパーソナルトークン% をBase64したもの | BASE64文字列
APPLE_APP_ID | アプリケーションのバンドルID | com.example.app-name
APPLE_TEAM_ID | Apple Developer プログラムのチームID | F946... のような英数字
APPLE_KEY_ID |  | 10桁程度の大文字英数
APPLE_ISSUER_ID | XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX のような16進
APPLE_KEY_CONTENT | -----BEGIN PRIVATE KEY----- で始まる秘密鍵

## 手作業で対応が必要な部分

### Gemfile.lockの生成

Gemfileをどこかからコピーし、以下のコマンドを実行する

```
docker run --rm -ti -v $(pwd):/src ruby:2.7 bash
cd /src
bundle install
```
