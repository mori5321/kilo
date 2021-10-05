# compiler_setting.json の 更新方法
- Makefile の kilo コマンドを編集
- bear -- make


# ccls の 環境構築
extraArgs の部分に

```
"languageserver": {
      "ccls": {
      "command": "ccls",
      "filetypes": ["c", "cpp", "objc", "objcpp"],
      "rootPatterns": [".ccls", "compile_commands.json", ".vim/", ".git/", ".hg/"],
      "initializationOptions": {
         "client": {
          "snippetSupport": true
         },
         "cache": {
           "directory": "/tmp/ccls"
         },
         "clang": {
          "resourceDir": "/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/clang/12.0.0/include",
          "extraArgs": [
            "-std=c++2a",
            "-isysroot", "/Library/Developer/CommandLineTools/SDKs/MacOSX.sdk/usr/include",
            "-isystem", "/Library/Developer/CommandLineTools/usr/include/c++/v1",
          ]
        }
       }
    }
  }
```

以下の記事を参考に値を入れる。
MacOSのところ参照

https://github.com/MaskRay/ccls/wiki/Build
