# RE2 2021-02-02 on loongarch64

    cmake -B build -DCMAKE_INSTALL_PREFIX=$PREFIX -DCMAKE_BUILD_TYPE=Release \
          -DCMAKE_POSITION_INDEPENDENT_CODE=ON .
    cmake --build build -j4 && cmake --install build

零补丁。这个版本（2021-02-02）**不依赖 abseil**，构建很轻。

它同时是 hyperscan 兼容层的后端（见 `hyperscan-shim-loongarch64`）。

## 更新（2026-11-04）

作为 hyperscan 兼容层的后端，`libhs.a` 链接进 `doris_be` 后，LIKE / REGEXP / MATCH_ANY / MATCH_ALL
相关目标全部编译通过，0 undefined symbol；启动验证中相关服务正常加载。
