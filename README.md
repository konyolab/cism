# CISM

Intensity Segment Modulation (ISM) [[1]][ISM]と立体振動技術の実装とサンプルプログラム．

## 公開予定

- WIN64
  - Windows用のコンパイル済みDLL
    - ism-core.dll
    - ism-mx.dll
  - インポートライブラリ
    - ism-core.lib
    - ism-mx.lib
  - 静的ライブラリ
    - ism-core-static.lib
    - ism-mx-static.lib
- OSX
  - macOS用コンパイル済み共有ライブラリ
    - libism-core.dylib
    - libism-mx.dylib
  - 静的ライブラリ
    - libism-core.a
    - libism-mx.a
- LINUX
  - Linux (Ubuntu 20.04で動作確認)用のコンパイル済み共有ライブラリ
    - libism-core.so
    - libism-mx.so
  - 静的ライブラリ
    - libism-core.a
    - libism-mx.a
- examples
  - CMakeでコンパイル可能なサンプルプログラム
  - ism-audio-converter
    - ISMによる音声ファイルの変換プログラム
  - ism-rt
    - ISMとPortAudioによるリアルタイム変換プログラム
- CMakeLists.txt

## 使用方法

通常の外部ライブラリのリンク方法に準じる．gccなら`-lism-core`など，
CMakeなら`target_link_libraries(${TARGET_NAME} PRIVATE ism-core)`などと書く．

その他の方法として，以下に示すようにCMakeのFetchContentによる取り込みに対応する予定である．

```CMake
FetchContent_Declare(
    ism
    GIT_REPOSITORY https://github.com/konyolab/cism.git
)
FetchContent_MakeAvailable(ism)
```

[ISM]: https://ieeexplore.ieee.org/abstract/document/9517147
