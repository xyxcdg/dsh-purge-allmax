# 1.0.0

首个独立发行版。基于社区版 1.6.84 的全部能力，作为自包含插件（`dsh-purge-allmax`）独立发布，不再依赖社区包作为底层。

- **能力对齐**：完整继承社区版 1.6.84 的 79 条拒绝检测规则、reasoning 分支、抢救式重放（salvage-replay）、尾部强化段、四层提示词注入、左侧栏整页设置、redteam 与 presets。
- **核心增强**：拒绝重试链路与检测器在自包含包内独立维护，可单独迭代升级，不受上游发布节奏限制。
- **向前兼容**：`dsh.compatibility` 放开对上界的锁定（`>=0.2.1-rc.1`），兼容探测仅告警、不阻断，后续 DSH / agent 版本升级无需改代码即可加载。
- **包身份**：`name=dsh-purge-allmax`，命令入口 `purge-community` / `purge-allmax` 双别名；审计目录独立为 `dsh-purge-allmax`（遵循 `DSH_HOME`），与社区版互不覆盖。

与社区版并存会重复注入提示词并触发 cordis 的 `next() called multiple times`，因此安装本版时应移除社区版，仅保留本插件。
