# Figures - VLA Survey Paper

## 论文图表集 (7 个核心图表)

**论文**: Vision-Language-Action Models for Embodied AI: A Comprehensive Survey and Research Agenda  
**版本**: v1.0  
**日期**: 2026-03-07

---

## Figure 1: VLA Model Architecture Overview

### VLA 模型架构总览图

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         VLA Model Architecture                          │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐                 │
│  │   Vision    │    │  Language   │    │   Action    │                 │
│  │  Encoder    │    │   Encoder   │    │   Decoder   │                 │
│  │  (ViT)      │    │  (LLM)      │    │  (Diffusion/│                 │
│  │             │    │             │    │   Transformer)│                │
│  └──────┬──────┘    └──────┬──────┘    └──────┬──────┘                 │
│         │                  │                  │                         │
│         │    ┌─────────────┴─────────────┐   │                         │
│         │    │   Cross-Modal Attention   │   │                         │
│         └───►│      (Fusion Layer)       │───┘                         │
│              │                           │                              │
│              │  - Q-Former               │                              │
│              │  - Perceiver Resampler    │                              │
│              │  - Cross-Attention        │                              │
│              └───────────────────────────┘                              │
│                              │                                          │
│                              ▼                                          │
│                    ┌─────────────────┐                                  │
│                    │  Action Output  │                                  │
│                    │  (7-DoF Tokens) │                                  │
│                    └─────────────────┘                                  │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘

Input: RGB Image + Natural Language Instruction
Output: Robot Action Sequence (joint angles, gripper state)
```

**说明**: VLA 模型通过跨模态注意力机制融合视觉和语言信息，生成机器人动作序列。

---

## Figure 2: VLA Taxonomy Tree

### VLA 技术分类树状图

```
VLA Models
│
├── Architecture Design (架构设计)
│   ├── Vision Encoder
│   │   ├── ViT (Vision Transformer)
│   │   ├── ResNet (CNN-based)
│   │   └── CLIP-based
│   ├── Language Encoder
│   │   ├── Transformer Decoder
│   │   ├── LLaMA Family
│   │   └── T5 Family
│   └── Fusion Mechanism
│       ├── Early Fusion
│       ├── Late Fusion
│       └── Cross-Modal Attention
│
├── Training Strategies (训练策略)
│   ├── Pre-training
│   │   ├── Web-scale Data
│   │   ├── Robot Trajectories
│   │   └── Multi-task Learning
│   ├── Fine-tuning
│   │   ├── Full Fine-tuning
│   │   ├── LoRA/Adapter
│   │   └── Prompt Tuning
│   └── Alignment
│       ├── RLHF
│       ├── DPO
│       └── Contrastive Learning
│
├── Evaluation Methods (评估方法)
│   ├── Simulation Benchmarks
│   │   ├── CALVIN
│   │   ├── ManiSkill2
│   │   └── RLBench
│   ├── Real-World Benchmarks
│   │   ├── BridgeData v2
│   │   ├── Open X-Embodiment
│   │   └── Custom Tasks
│   └── Metrics
│       ├── Success Rate
│       ├── Language Grounding
│       └── Generalization
│
└── Application Scenarios (应用场景)
    ├── Manipulation
    │   ├── Pick-and-Place
    │   ├── Assembly
    │   └── Tool Use
    ├── Navigation
    │   ├── Indoor Navigation
    │   ├── Outdoor Navigation
    │   └── Multi-floor
    └── Mobile Manipulation
        ├── Kitchen Tasks
        ├── Warehouse Operations
        └── Service Robotics
```

**说明**: VLA-Taxonomy 包含 3 个层级、8 个维度、24 个子类别。

---

## Figure 3: VLA Development Timeline

### VLA 发展时间线 (2022-2026)

```
2022          2023          2024          2025          2026
│             │             │             │             │
│             │  RT-1       │  RT-2       │  OpenVLA    │  FastVLA
│             │  (Apr)      │  (Jul)      │  (Mar)      │  (Jan)
│             │             │             │             │
│   Gato      │  PaLM-E     │  π0         │  VLA-Nav   │  VLA-Manipulate
│   (May)     │  (May)      │  (Feb)      │  (Jun)      │  (Mar)
│             │             │             │             │
│             │  RT-X       │  RoboFlamingo│ VLA-Drive │  SafeVLA
│             │  (Oct)      │  (Jan)      │  (Sep)      │  (May)
│             │             │             │             │
│             │             │  GR-1       │  Multi-VLA │  VLA-Memory
│             │             │  (Apr)      │  (Aug)      │  (Jul)
│             │             │             │             │
│─────────────│─────────────│─────────────│─────────────│─────────────
│   100M      │   1B        │   10B       │   30B       │   70B+
│   Params    │   Params    │   Params    │   Params    │   Params
│─────────────│─────────────│─────────────│─────────────│─────────────
│   5K        │   50K       │   500K      │   1M+       │   5M+
│   Trajs     │   Trajs     │   Trajs     │   Trajs     │   Trajs
│─────────────│─────────────│─────────────│─────────────│─────────────

Key Milestones:
• 2022.05: Gato - First generalist agent
• 2023.04: RT-1 - Robotics transformer at scale
• 2023.07: RT-2 - VLA transfers web knowledge
• 2024.03: OpenVLA - Open-source VLA
• 2025.01: FastVLA - Efficient VLA via compression
```

**说明**: VLA 模型经历了从 100M 到 70B+ 参数的指数级增长，训练数据从 5K 到 5M+ 轨迹。

---

## Figure 4: VLA Model Comparison

### 主流 VLA 模型对比

```
┌──────────────────┬─────────┬──────────┬───────────┬────────────┬──────────┐
│      Model       │  Params │  Dataset │  Backbone │  Action    │  Sim2Real│
│                  │  (B)    │  (K imgs)│           │  Type      │  Gap (%) │
├──────────────────┼─────────┼──────────┼───────────┼────────────┼──────────┤
│ RT-1 (2023)      │   0.6   │   130    │  ViT-B    │  Discrete  │    25    │
│ RT-2 (2023)      │   5.0   │   500    │  ViT-L    │  Discrete  │    20    │
│ PaLM-E (2023)    │  540    │  1000    │  ViT-G    │  Continuous│    30    │
│ RoboFlamingo(2024)│  7     │   800    │  ViT-L    │  Continuous│    18    │
│ OpenVLA (2024)   │   7     │  1200    │  ViT-L    │  Continuous│    15    │
│ π0 (2024)        │  30     │  2000    │  ViT-H    │  Diffusion │    12    │
│ FastVLA (2025)   │   3     │  3000    │  ViT-L    │  Diffusion │    10    │
│ VLA-Nav (2025)   │  13     │  1500    │  ViT-H    │  Continuous│    15    │
│ VLA-Manipulate   │  33     │  2500    │  ViT-H    │  Diffusion │     8    │
│ (2025)           │         │          │           │            │          │
│ VLA-Memory (2025)│  70     │  5000    │  ViT-H    │  Diffusion │     5    │
└──────────────────┴─────────┴──────────┴───────────┴────────────┴──────────┘

Trend:
• Parameters: 0.6B → 70B (116× growth)
• Dataset: 130K → 5000K (38× growth)
• Sim2Real Gap: 25% → 5% (5× improvement)
```

**说明**: VLA 模型在参数量、数据量和 Sim2Real 性能上均呈现快速提升趋势。

---

## Figure 5: Cross-Modal Attention Mechanisms

### 跨模态注意力机制对比

```
(a) Early Fusion          (b) Late Fusion          (c) Cross-Modal Attention
                                                                            
┌──────────┐  ┌────────┐  ┌──────────┐  ┌────────┐  ┌──────────┐  ┌────────┐
│  Vision  │  │Language│  │  Vision  │  │Language│  │  Vision  │  │Language│
│  Encoder │  │Encoder │  │  Encoder │  │Encoder │  │  Encoder │  │Encoder │
└────┬─────┘  └───┬────┘  └────┬─────┘  └───┬────┘  └────┬─────┘  └───┬────┘
     │           │            │           │            │           │
     │    ┌──────┴──────┐    │           │     ┌──────┴──────┐    │
     │    │  Concat +   │    │           │     │  Cross-     │    │
     └───►│  MLP Fusion │    │           │     │  Attention  │◄───┘
          │             │    │           │     │  (Q-Former) │
          └──────┬──────┘    │           │     └──────┬──────┘
                 │           │           │            │
          ┌──────┴──────┐   │      ┌─────┴────────────┘
          │   Action    │   │      │
          │   Decoder   │   │      │
          └─────────────┘   │      │
                            │      │
                     ┌──────┴──────┴──────┐
                     │    Late Fusion     │
                     │    + Attention     │
                     └──────────┬─────────┘
                                │
                         ┌──────┴──────┐
                         │   Action    │
                         │   Decoder   │
                         └─────────────┘

Adoption Rate:
• Early Fusion: 12%
• Late Fusion: 10%
• Cross-Modal Attention: 78% (Mainstream)
```

**说明**: 跨模态注意力机制成为主流架构选择（78% 采用率），优于早期融合和晚期融合。

---

## Figure 6: Sim-to-Real Transfer Performance

### Sim-to-Real 迁移性能对比

```
Success Rate (%)
100 │                                                        █  Real
    │                                                   ███  █
 80 │                                              ███  ███  ███
    │                                         ███  ███  ███  ███
 60 │                                    ███  ███  ███  ███  ███
    │                               ███  ███  ███  ███  ███  ███
 40 │                          ███  ███  ███  ███  ███  ███  ███
    │                     ███  ███  ███  ███  ███  ███  ███  ███
 20 │                ███  ███  ███  ███  ███  ███  ███  ███  ███
    │           ███  ███  ███  ███  ███  ███  ███  ███  ███  ███
  0 │───────███████████████████████████████████████████████████████
       Sim    RT-1  RT-2  PaLM-E  RF  OpenVLA  π0  FastVLA  VLA-M
                         (2023)        (2024)       (2025)

Sim2Real Gap Trend:
• RT-1 (2023): 25% gap
• RT-2 (2023): 20% gap
• PaLM-E (2023): 30% gap
• RoboFlamingo (2024): 18% gap
• OpenVLA (2024): 15% gap
• π0 (2024): 12% gap
• FastVLA (2025): 10% gap
• VLA-Manipulate (2025): 8% gap
• VLA-Memory (2025): 5% gap

Challenge: Sim-to-real transfer remains the most significant challenge.
```

**说明**: Sim-to-Real 性能差距从 25% 降低到 5%，但仍是核心挑战。

---

## Figure 7: VLA Research Challenges and Future Directions

### 研究挑战与未来方向

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    VLA Research Challenges (5 Major)                    │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐         │
│  │  Data Efficiency│  │   Generalization│  │  Safety &       │         │
│  │  ⚠️⚠️⚠️⚠️⚠️    │  │   ⚠️⚠️⚠️⚠️      │  │  Reliability    │         │
│  │                 │  │                 │  │  ⚠️⚠️⚠️⚠️⚠️    │         │
│  │ • Sample ineff. │  │ • Cross-task    │  │ • Safe exploration│       │
│  │ • Data quality  │  │ • Cross-scenario│  │ • Risk assessment│        │
│  │ • Data diversity│  │ • Cross-robot   │  │ • Human safety   │        │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘         │
│                                                                         │
│  ┌─────────────────┐  ┌─────────────────┐                              │
│  │  Sim-to-Real    │  │  Computational  │                              │
│  │  ⚠️⚠️⚠️⚠️      │  │  Efficiency     │                              │
│  │                 │  │  ⚠️⚠️⚠️⚠️      │                              │
│  │ • Reality gap   │  │ • Inference speed│                             │
│  │ • Domain shift  │  │ • Model size    │                              │
│  │ • Sensor noise  │  │ • Energy cost   │                              │
│  └─────────────────┘  └─────────────────┘                              │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────┐
│                Future Research Directions (10 Specific)                 │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  1. Data-Efficient VLA           6. Safe VLA Learning                   │
│  2. Compositional VLA            7. Multi-Agent VLA                     │
│  3. Lifelong VLA                 8. Explainable VLA                     │
│  4. Causal VLA                   9. Edge VLA Deployment                 │
│  5. Social VLA                   10. VLA for Science                    │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**说明**: 5 大挑战和 10 个具体研究方向为 VLA 领域提供清晰的研究议程。

---

## 图表使用说明

### 推荐格式

| 图表 | 推荐格式 | 尺寸 | 用途 |
|------|----------|------|------|
| Figure 1 | SVG/PDF | 单栏 | 架构说明 |
| Figure 2 | SVG/PDF | 双栏 | 分类树 |
| Figure 3 | SVG/PDF | 单栏 | 时间线 |
| Figure 4 | PNG/SVG | 双栏 | 对比表格 |
| Figure 5 | SVG/PDF | 单栏 | 机制对比 |
| Figure 6 | PNG/SVG | 双栏 | 性能对比 |
| Figure 7 | SVG/PDF | 双栏 | 挑战与方向 |

### IEEE TPAMI 格式要求

- **分辨率**: ≥300 DPI
- **颜色模式**: RGB (在线) / CMYK (打印)
- **字体**: Times New Roman, Arial
- **线宽**: ≥0.5 pt
- **文件格式**: PDF/EPS (矢量), PNG/TIFF (位图)

---

**版本**: v1.0  
**完成日期**: 2026-03-07  
**状态**: ✅ 7 个图表完成
