## Google Test 環境構築注意点
- [google/googletest: Google Test](https://github.com/google/googletest)
- 構築には次のページを参考にした。
  - [googletest/googletest at master · google/googletest](https://github.com/google/googletest/tree/master/googletest)
  - [google test のインストールでハマったのでメモ - Qiita](http://qiita.com/medaka5/items/171e10d5fa2d5e04f860)

## 実行の確認
```bash
vagrant up
vagrant ssh
# 共有フォルダで確認
cd /vagrant
cat << 'EOS' > test1.cpp
#include "gtest/gtest.h"

TEST(Test1, test11)
{
    ASSERT_EQ(1, 1);
}
EOS
# ビルド
g++ test1.cpp -I$GTEST_INCLUDEDIR -L$GTEST_LIBDIR -lgtest -lgtest_main -lpthread
# テスト実施
./a.out
```

次のように出力されれば成功
```bash
[vagrant@localhost vagrant]$ ./a.out
Running main() from gtest_main.cc
[==========] Running 1 test from 1 test case.
[----------] Global test environment set-up.
[----------] 1 test from Test1
[ RUN      ] Test1.test11
[       OK ] Test1.test11 (0 ms)
[----------] 1 test from Test1 (0 ms total)

[----------] Global test environment tear-down
[==========] 1 test from 1 test case ran. (1 ms total)
[  PASSED  ] 1 test.
[vagrant@localhost vagrant]$ 
```