---
title: "建立第一個 Hugo Blog"
date: 2023-02-04T01:53:28+08:00
draft: false
---

## 建立步驟

1. [Hugo Quick Start](https://gohugo.io/getting-started/quick-start/)

2. [Download Theme](https://themes.gohugo.io/themes/holy/)

3. [Host on GitHub](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

    ```sh
    hugo new site {YOUR_WORKSPACE}
    cd {YOUR_WORKSPACE}
    git init
    git submodule add https://github.com/serkodev/holy.git themes/holy

    cd public
    git branch -M main
    git remote add origin https://github.com/{USER_ACCOUNT}/{USER_ACCOUNT}.github.io.git
    git add .
    git commit -m "init website"
    git push -u origin main
    ```

4. 建立 "About" 頁面

    1. 建立 markdown 檔案 `hugo new content/about.md`

    2. 將草稿標籤更新 `draft: false`

    3. 修改 `config.toml`

        ```sh
        baseURL = 'http://{USER_ACCOUNT}.github.io/'
        title = '{YOUR_TITLE}'
        theme = 'holy'
        languageCode = 'zh-tw'
        DefaultContentLanguage = 'zh-tw'

        [menu]

        [[menu.main]]
            identifier = "about"
            name = "About"
            url = "/about/"
            weight = 10
        ```

    4. 執行 `hugo` 來編譯到 public
