# 次のような過程を経て修正お願いします。 
 
1. 修正する内容を要約したIssue作成
2. Issue番号に対するbranch生成 
```
i.e., branch name: pntml-# (# is issue number)
```
3. 当該branchで修正及びcommit 
4. 修正が完了すると、Push及びPull-request生成

- Pull-requestを作成するときは、関連するissueをdevelopmentに追加します。([例](https://github.com/dprtairc/pntml/pull/3))
- [@TaehoonK](https://github.com/TaehoonK)をreviewerに追加していただければ、後で確認してmergeすることにします。
 
5. これ以上使用されなさそうな場合にはbranch削除 

# 開発環境構築

`package.json` と `package-lock.json` からパッケージをインストール

```npm ci```

`redoc-cli` を使ってHTMLを生成して，生成されたHTMLを確認
```
./node_modules/.bin/redoc-cli bundle -o ./target/html/mf-api.html ./docs/mf/mf-api.yml
./node_modules/.bin/redoc-cli bundle -o ./target/html/pcm-api.html ./docs/pcm/pcm-api.yml
./node_modules/.bin/redoc-cli bundle -o ./target/html/pntml-api.html ./docs/pntml-open/pntml-api.yml
```

`redoc-cli` の実行は以下でも実行可能
```
npm run bundle_mf
npm run bundle_pcm
npm run bundle_common
```

