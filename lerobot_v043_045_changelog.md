# LeRobot 0.43 → 0.45 更新文档

> 版本对应: 0.43 = v0.4.3, 0.44 = v0.4.4, 0.45 = v0.4.5 (如存在)
> 本文档涵盖 v0.4.3 ~ v0.4.4 的主要更新

---

## 📌 版本概览

| 版本 | 发布类型 | 主要特性 |
|------|----------|----------|
| v0.4.3 | 功能更新 | 新机器人支持、PEFT训练支持、IsaacLab集成 |
| v0.4.4 | 优化更新 | SmolVLA torch.compile、异步推理、流式视频编码 |

---

## 🤖 新增机器人

### 1. Unitree G1 人形机器人
- **PR**: [#2530](https://github.com/huggingface/lerobot/pull/2530) - Feat/add unitree g1 robot
- **功能**: 添加 Unitree G1 人形机器人的完整支持
- **代码位置**: `lerobot/robots/`

### 2. OpenARM 系列
- **PR**: [#2795](https://github.com/huggingface/lerobot/pull/2795) - Feat(robots): add OpenArm robot & teleoperator
- **PR**: [#3022](https://github.com/huggingface/lerobot/pull/3022) - Feat(teleoperators): add OpenArm Mini teleoperator
- **功能**: 添加 OpenARM 和 OpenARM Mini 遥操作设备支持

### 3. OMX 机器人
- **PR**: [#2614](https://github.com/huggingface/lerobot/pull/2614) - feat(robot): Add support for OMX robot
- **代码位置**: `lerobot/robots/omx_robot.py`

### 4. Earth Rover
- **PR**: [#2575](https://github.com/huggingface/lerobot/pull/2575) - feat(robots): add earth rover robot support
- **PR**: [#2544](https://github.com/huggingface/lerobot/pull/2544) - Earth Rover Mini Plus integration

### 5. SO-101 双手机器人
- **PR**: [#2835](https://github.com/huggingface/lerobot/pull/2835) - feat(robots): add bi manual openarm follower and leader
- **PR**: [#2763](https://github.com/huggingface/lerobot/pull/2763) - feat(robots): consolidate SO arms implementation

### 6. G1 遥操作改进
- **PR**: [#2791](https://github.com/huggingface/lerobot/pull/2791) - add g1 teleoperation

---

## 🧠 新增策略 (Policies)

### 1. X-VLA (XVLA)
- **PR**: [#2405](https://github.com/huggingface/lerobot/pull/2405) - feat(policies): Add X-VLA
- **文档**: [xvla.mdx](./docs/source/xvla.mdx)
- **功能**: 跨具身视觉语言动作模型

### 2. Pi0Fast
- **PR**: [#2734](https://github.com/huggingface/lerobot/pull/2734) - feat(policies): add autoregressive VLAs with tokenization PiFast
- **文档**: [pi0fast.mdx](./docs/source/pi0fast.mdx)
- **功能**: 快速自回归 VLA 模型

### 3. SmolVLA + torch.compile 支持
- **PR**: [#3043](https://github.com/huggingface/lerobot/pull/3043) - feat(policies): add Smolvla torch compile support
- **PR**: [#3029](https://github.com/huggingface/lerobot/pull/3029) - Fix: remove device_map from SmolVLA model loading
- **功能**: SmolVLA 模型现支持 torch.compile 加速推理

### 4. DiffusionPolicy torch.compile
- **PR**: [#2486](https://github.com/huggingface/lerobot/pull/2486) - feat: Enable torch.compile for DiffusionPolicy inference
- **功能**: DiffusionPolicy 推理性能大幅提升

### 5. GR00T N1.5
- **文档**: [policy_groot_README.md](./docs/source/policy_groot_README.md)
- **功能**: Hugging Face GR00T N1.5 机器人策略支持

---

## 🔄 异步推理 (Async Inference)

- **PR**: [#2425](https://github.com/huggingface/lerobot/pull/2425) - feat(async_inference) Enable plugins with async inference
- **功能**: 
  - 支持插件式异步推理
  - 改进服务器-客户端流式传输
- **PR**: [#2792](https://github.com/huggingface/lerobot/pull/2792) - fix: ensure action tensors are moved to client_device in async training

---

## 📊 数据集 (Dataset) 改进

### 1. 流式视频编码 + 硬件编码器支持
- **PR**: [#2974](https://github.com/huggingface/lerobot/pull/2974) - feat(dataset): add streaming video encoding + HW encoder support
- **功能**: 支持硬件加速视频编码，大幅提升录制性能

### 2. metadata_buffer_size 参数
- **PR**: [#2998](https://github.com/huggingface/lerobot/pull/2998) - add metadata_buffer_size to dataset creation
- **功能**: 数据集创建时可配置元数据缓冲区大小

### 3. 动态压缩级别
- **PR**: [#2517](https://github.com/huggingface/lerobot/pull/2517) - feat(dataset): dynamic compress_level depending on the type of dataset
- **功能**: 根据数据集类型（视频或图像）自动调整压缩级别

### 4. 编码速度优化
- **PR**: [#2514](https://github.com/huggingface/lerobot/pull/2514) - feat(dataset): speed-up encoding time
- **PR**: [#2525](https://github.com/huggingface/lerobot/pull/2525) - feat(parallel encoding): making parallel encoding the default choice

### 5. 并行编码默认启用
- **PR**: [#2525](https://github.com/huggingface/lerobot/pull/2525) - feat(parallel encoding): making parallel encoding the default choice over all platforms

### 6. 数据集工具增强
- **PR**: [#2560](https://github.com/huggingface/lerobot/pull/2560) - feat(dataset): add tool to convert images to video datasets
- **PR**: [#2875](https://github.com/huggingface/lerobot/pull/2875) - Feat(dataset_tools.py) Add modify tasks tool

---

## 🎮 模拟环境 (Simulation)

### 1. IsaacLab Arena 集成
- **PR**: [#2699](https://github.com/huggingface/lerobot/pull/2699) - feat(envs): Add NVIDIA IsaacLab-Arena Lerobot
- **PR**: [#2749](https://github.com/huggingface/lerobot/pull/2749) - IsaacLab Arena Integration documentation update
- **文档**: [lerobot-envhub](./docs/source/envhub)
- **功能**: 支持 NVIDIA IsaacLab 高性能仿真环境

### 2. EnvHub 统一接口
- **PR**: [#2121](https://github.com/huggingface/lerobot/pull/2121) - feat(sim): EnvHub - allow loading envs from the hub
- **功能**: 从 Hugging Face Hub 加载仿真环境

### 3. Gym-HIL 集成修复
- **PR**: [#2482](https://github.com/huggingface/lerobot/pull/2482) - Fix gym-hil integration with the new LeRobot pipeline

### 4. LIBERO 基准支持
- **PR**: [#2888](https://github.com/huggingface/lerobot/pull/2888) - fix(pipeline): use FeatureType for STATE features in Libero processor
- **PR**: [#2899](https://github.com/huggingface/lerobot/pull/2899) - Change LIBERO init_state_id when reset
- **PR**: [#2817](https://github.com/huggingface/lerobot/pull/2817) - fix libero reset logic for correct resetting

---

## 🛠️ 训练 (Training) 改进

### 1. PEFT (参数高效微调) 支持
- **PR**: [#1411](https://github.com/huggingface/lerobot/pull/1411) - Add basic PEFT support to train script + record module
- **PR**: [#2806](https://github.com/huggingface/lerobot/pull/2806) - Refactor: Move PEFT config from training script to policy level
- **功能**: 支持 LoRA 等 PEFT 方法进行高效微调

### 2. tqdm 进度条集成
- **PR**: [#3010](https://github.com/huggingface/lerobot/pull/3010) - feat(scripts): Integrate tqdm for training progress visualization
- **功能**: 训练过程可视化进度条

### 3. 精确睡眠优化
- **PR**: [#2526](https://github.com/huggingface/lerobot/pull/2526) - feat(utils): precise_sleep() less CPU hungry without sacrificing accuracy
- **功能**: 更低 CPU 占用的精确时间控制

### 4. 多观察步骤支持
- **PR**: [#2430](https://github.com/huggingface/lerobot/pull/2430) - fix(policies): support dp train when n_obs_steps=1

### 5. 日志修复
- **PR**: [#3045](https://github.com/huggingface/lerobot/pull/3045) - fix(logging): avoid double-counting samples across processes

---

## 🔌 电机与硬件 (Motors)

### 1. RobStride CAN 电机
- **PR**: [#2821](https://github.com/huggingface/lerobot/pull/2821) - feat(motors): add RobStride CAN implementation

### 2. Damiao 电机 & CAN 总线
- **PR**: [#2788](https://github.com/huggingface/lerobot/pull/2788) - feat(motors): add damiao motors & can bus

### 3. Robot 上下文管理器
- **PR**: [#2828](https://github.com/huggingface/lerobot/pull/2828) - feat(robots): add context managers
- **功能**: 支持 `with robot:` 语法

---

## 🏷️ 第三策略支持

- **PR**: [#2308](https://https://github.com/huggingface/lerobot/pull/2308) - feat(policies): Allow users to register 3rd party policies
- **功能**: 支持通过 `pip install lerobot_policy_mypolicy` 安装第三方策略

---

## 📝 其他重要修复

| PR | 描述 |
|----|------|
| [#3046](https://github.com/huggingface/lerobot/pull/3046) | Fix(diffusion): enforce no-crop behavior when crop_ratio=1.0 |
| [#3016](https://github.com/huggingface/lerobot/pull/3016) | fix(video): replace assertions with proper exceptions |
| [#3017](https://github.com/huggingface/lerobot/pull/3017) | Fix metaworld_config.json not bundled in pip installs |
| [#2548](https://github.com/huggingface/lerobot/pull/2548) | fix(dataset): Fix reindexing bug for videos on splits |
| [#2456](https://github.com/huggingface/lerobot/pull/2456) | Fix episode filtering bug when requesting a subset |

---

## 📦 依赖更新

- **PyTorch**: 更新到支持 torch.compile 的版本
- **WandB & Protobuf**: 升级到更新版本 ([#2800](https://github.com/huggingface/lerobot/pull/2800))
- **Datasets**: 升级 ceil datasets ([#2946](https://github.com/huggingface/lerobot/pull/2946))

---

## 📚 文档更新

- 添加 WSL evdev 安装说明 ([#2855](https://github.com/huggingface/lerobot/pull/2855))
- 更新 Phone 遥操作文档 ([#2991](https://github.com/huggingface/lerobot/pull/2991))
- X-VLA 训练策略/命令文档 ([#2611](https://github.com/huggingface/lerobot/pull/2611))
- 现代化 README 设计 ([#2660](https://github.com/huggingface/lerobot/pull/2660))

---

## 🔧 代码位置索引

```
lerobot/
├── robots/                    # 机器人实现
│   ├── unitree_g1.py          # Unitree G1
│   ├── openarm.py             # OpenARM
│   ├── omx_robot.py           # OMX
│   ├── earth_rover.py         # Earth Rover
│   └── so101_follower.py      # SO-101
├── policies/                  # 策略实现
│   ├── xvla/                  # X-VLA
│   ├── pi0fast/               # Pi0Fast
│   ├── smolvla/               # SmolVLA
│   └── diffusion/             # DiffusionPolicy
├── datasets/                  # 数据集处理
│   ├── lerobot_dataset.py     # LeRobotDataset
│   └── dataset_utils.py       # 工具函数
├── envs/                      # 仿真环境
│   ├── isaaclab/              # IsaacLab
│   └── envhub/                # EnvHub
└── scripts/                   # 训练/评估脚本
    ├── lerobot_train.py
    └── lerobot_eval.py
```

---

## 🚀 升级建议

1. **如果使用 DiffusionPolicy**: 建议启用 torch.compile 获得性能提升
2. **如果使用 SmolVLA**: 更新到最新版本以获得 torch.compile 支持
3. **如果使用数据集**: 新版本的流式编码和并行编码可显著提升性能
4. **如果要添加自定义策略**: 使用新的插件系统

---

*文档生成时间: 2026-03-02*
*基于 Git commit: v0.4.0 → v0.4.4*
