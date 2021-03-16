---
title: Using private NPM modules
sidebar_label: Using Private NPM modules
previousText: 'Using private Git repositories'
previousUrl: '/docs/appflow/cookbook/private_git'
nextText: 'Private Native Plugin Keys'
nextUrl: '/docs/appflow/cookbook/private-native-enterprise-keys'
---

使用 npm CLI 获取验证码：

    $ npm token create --read-only
    npm password:
    ┌────────────────┬──────────────────────────────────────┐
    │ token          │ 1a583a54-5515-4058-a3c4-047e5f699d27 │
    ├────────────────┼──────────────────────────────────────┤
    │ cidr_whitelist │                                      │
    ├────────────────┼──────────────────────────────────────┤
    │ readonly       │ true                                 │
    ├────────────────┼──────────────────────────────────────┤
    │ created        │ 2019-01-08T20:53:17.461Z             │
    └────────────────┴──────────────────────────────────────┘
    

在Appflow环境中配置一个`NPM_TOKEN`密钥，使用生成的令牌作为值:

![NPM 令牌密钥](/docs/assets/img/appflow/cookbook/npm-token-secret.png)

在项目目录根目录中检查`.npmrc`文件如下行：

    //registry.npmjs.org/:_authToken=${NPM_TOKEN}