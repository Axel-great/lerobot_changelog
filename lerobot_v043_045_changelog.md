# LeRobot 更新文档 (2025.12.29 → v0.4.4)

> 基于你当前的 2025.12.29 版本，对应约 v0.4.2 ~ v0.4.3
> 最新版本: v0.4.4 (2026-02-27)

---

## 🤖 新增机器人

| 机器人 | PR | 描述 |
|--------|-----|------|
| Unitree G1 | [#2530](https://github.com/huggingface/lerobot/pull/2530) | 人形机器人完整支持 |
| OpenARM | [#2795](https://github.com/huggingface/lerobot/pull/2795) | 机械臂遥操作 |
| OpenARM Mini | [#3022](https://github.com/huggingface/lerobot/pull/3022) | Mini 版遥操作设备 |
| OMX | [#2614](https://github.com/huggingface/lerobot/pull/2614) | OMX 机器人支持 |
| G1 双手机器人 | [#2791](https://github.com/huggingface/lerobot/pull/2791) | G1 遥操作改进 |
| Earth Rover | [#2575](https://github.com/huggingface/lerobot/pull/2575) | 地面 rover |
| SO-101 双臂 | [#2835](https://github.com/huggingface/lerobot/pull/2835) | 双臂协调支持 |

---

## 🧠 策略 (Policies) 更新

### 性能优化
- **SmolVLA torch.compile** ([#3043](https://github.com/huggingface/lerobot/pull/3043)) - 推理加速
- **DiffusionPolicy torch.compile** ([#2486](https://github.com/huggingface/lerobot/pull/2486)) - 推理加速

### 新模型
- **X-VLA** ([#2405](https://github.com/huggingface/lerobot/pull/2405)) - 跨具身视觉语言动作模型
- **Pi0Fast** ([#2734](https://github.com/huggingface/lerobot/pull/2734)) - 快速自回归 VLA

### Pi0 / Pi0.5 改进
- 新增 `freeze_vision_encoder` 参数
- 新增 `train_expert_only` 训练模式

### Bug 修复
- **n_obs_steps=1** ([#2430](https://github.com/huggingface/lerobot/pull/2430)) - DiffusionPolicy 多观察步骤支持
- **SmolVLA device_map** ([#3029](https://github.com/huggingface/lerobot/pull/3029)) - 修复模型加载

---

## 📊 数据集 (Dataset) 改进

### 性能
- **流式视频编码 + 硬件加速** ([#2974](https://github.com/huggingface/lerobot/pull/2974)) - 显著提升录制性能
- **并行编码默认启用** ([#2525](https://github.com/huggingface/lerobot/pull/2525))
- **动态压缩级别** ([#2517](https://github.com/huggingface/lerobot/pull/2517)) - 根据数据类型自动调整
- **编码速度优化** ([#2514](https://github.com/huggingface/lerobot/pull/2514))

### 功能
- **metadata_buffer_size** ([#2998](https://github.com/huggingface/lerobot/pull/2998)) - 配置元数据缓冲区
- **subtask 支持** ([#2860](https://github.com/huggingface/lerobot/pull/2860)) - 数据集子任务
- **图像转视频工具** ([#2560](https://github.com/huggingface/lerobot/pull/2560))
- **lerobot-edit-dataset** 增强 ([#2917](https://github.com/huggingface/lerobot/pull/2917), [#2875](https://github.com/huggingface/lerobot/pull/2875))

### Bug 修复
- **视频 reindexing** ([#2548](https://github.com/huggingface/lerobot/pull/2548))
- **episode filtering** ([#2982](https://github.com/huggingface/lerobot/pull/2982), [#2456](https://github.com/huggingface/lerobot/pull/2456))

---

## 🎮 模拟环境 (Simulation)

### IsaacLab Arena
- **集成 NVIDIA IsaacLab** ([#2699](https://github.com/huggingface/lerobot/pull/2699))
- **文档更新** ([#2749](https://github.com/huggingface/lerobot/pull/2749))

### EnvHub
- **统一环境接口** ([#2121](https://github.com/huggingface/lerobot/pull/2121)) - 从 Hugging Face Hub 加载环境

### 其他
- **Gym-HIL 集成修复** ([#2482](https://github.com/huggingface/lerobot/pull/2482))
- **LIBERO 多项修复** ([#2888](https://github.com/huggingface/lerobot/pull/2888), [#2899](https://github.com/huggingface/lerobot/pull/2899), [#2817](https://github.com/huggingface/lerobot/pull/2817))

---

## 🛠️ 训练 (Training) 改进

- **tqdm 进度条** ([#3010](https://github.com/huggingface/lerobot/pull/3010)) - 训练可视化
- **PEFT 支持** ([#1411](https://github.com/huggingface/lerobot/pull/1411), [#2806](https://github.com/huggingface/lerobot/pull/2806)) - LoRA 等参数高效微调
- **精确睡眠优化** ([#2526](https://github.com/huggingface/lerobot/pull/2526)) - 更低 CPU 占用
- **日志修复** ([#3045](https://github.com/huggingface/lerobot/pull/3045)) - 避免多进程重复计数

---

## 🔌 电机与硬件

- **RobStride CAN** ([#2821](https://github.com/huggingface/lerobot/pull/2821))
- **Damiao 电机** ([#2788](https://github.com/huggingface/lerobot/pull/2788))
- **Robot 上下文管理器** ([#2828](https://github.com/huggingface/lerobot/pull/2828)) - 支持 `with robot:` 语法

---

## 🔌 异步推理

- **插件式异步推理** ([#2425](https://github.com/huggingface/lerobot/pull/2425))
- **服务器-客户端流式传输** 改进 ([#2792](https://github.com/huggingface/lerobot/pull/2792))

---

## 📝 其他重要修复

| PR | 描述 |
|-----|------|
| [#3046](https://github.com/huggingface/lerobot/pull/3046) | Diffusion crop_ratio=1.0 无裁切 |
| [#3016](https://github.com/huggingface/lerobot/pull/3016) | Video frame 解码异常处理 |
| [#3017](https://github.com/huggingface/lerobot/pull/3017) | metaworld_config.json 打包修复 |
| [#3005](https://github.com/huggingface/lerobot/pull/3005) | 数据集卡片可视化徽章 |

---

## 📦 依赖更新

- PyTorch: 支持 torch.compile
- WandB & Protobuf: 升级
- Datasets: ceil datasets 升级

---

## 🚀 升级命令

```bash
pip install lerobot -U
```

---

*文档更新: 2026-03-02*
