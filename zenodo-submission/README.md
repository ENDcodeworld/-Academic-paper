# Zenodo 提交指南

**目的**：为 GitHub 仓库分配正式 DOI，使论文可正式引用

**网址**：https://zenodo.org

---

## 📋 什么是 Zenodo？

**Zenodo** 是由 CERN（欧洲核子研究中心）运营的学术存储库。

| 特点 | 说明 |
|------|------|
| **运营方** | CERN（欧洲核子研究中心） |
| **费用** | 完全免费 |
| **DOI** | 自动分配（正式可引用） |
| **审核** | 自动（即时发布） |
| **存储** | 永久保存 |
| **集成** | 与 GitHub 无缝集成 |

---

## 🚀 提交流程（15 分钟）

### Step 1：创建 Zenodo 账号（3 分钟）

1. 访问：https://zenodo.org
2. 点击 "Log in"
3. 选择 "Sign in with GitHub"（推荐）或 ORCID
4. 授权 Zenodo 访问 GitHub
5. 完成

**优势**：GitHub 登录，自动关联仓库

---

### Step 2：启用 GitHub 集成（2 分钟）

1. 登录后，点击右上角用户菜单
2. 选择 "GitHub"
3. 找到 `-Academic-paper` 仓库
4. 点击右侧的开关（启用）
5. 完成

**效果**：每次 GitHub release 自动创建 Zenodo 记录

---

### Step 3：创建 GitHub Release（5 分钟）

1. 访问：https://github.com/ENDcodeworld/-Academic-paper
2. 点击 "Releases" → "Create a new release"
3. 填写：
   - **Tag version**：v1.0
   - **Release title**：VLA Survey Paper v1.0 (Initial Release)
   - **Description**：
     ```
     Initial release of VLA survey paper.
     
     Content:
     - 8 chapters (55,200 words)
     - 100+ references
     - 15+ comparison tables
     - Submission guide for arXiv/IEEE TPAMI
     
     Target: arXiv preprint
     Date: 2026-03-06
     ```
   - **Choose a tag**：v1.0
4. 点击 "Publish release"

---

### Step 4：Zenodo 自动创建记录（自动）

**Zenodo 会自动**：
1. 检测到 GitHub release
2. 抓取仓库内容
3. 分配 DOI
4. 创建引用记录

**等待时间**：1-5 分钟

---

### Step 5：完善 Zenodo 记录（5 分钟）

1. 访问：https://zenodo.org/account/settings/github/
2. 找到刚创建的记录
3. 点击 "Edit"
4. 完善信息：

| 字段 | 内容 |
|------|------|
| **Title** | Vision-Language-Action Models for Embodied AI: A Comprehensive Survey and Research Agenda |
| **Creators** | [志哥姓名], 小志 2 号 |
| **Description** | First systematic survey of VLA models, covering 287 papers from 2023-2026. Proposes VLA-Taxonomy framework and identifies 5 core challenges with 10 future research directions. |
| **Publication date** | 2026-03-06 |
| **Publication type** | Preprint |
| **Language** | English |
| **Keywords** | Vision-Language-Action Models, Embodied AI, Robot Learning, Multi-modal Fusion, Systematic Survey, arXiv |
| **Related identifier** | arXiv:2603.XXXXX（发布后添加） |
| **License** | CC BY 4.0 |

5. 点击 "Save"
6. 点击 "Submit" → "Publish"

---

## 📊 DOI 获取

**发布后获得**：

```
DOI: 10.5281/zenodo.XXXXXXX
URL: https://doi.org/10.5281/zenodo.XXXXXXX
```

**引用格式**：

```bibtex
@software{zhi2026vla,
  author = {Zhi, [Name] and Xiao, Zhi 2nd},
  title = {Vision-Language-Action Models for Embodied AI: A Comprehensive Survey and Research Agenda},
  month = {3},
  year = {2026},
  publisher = {Zenodo},
  version = {v1.0},
  doi = {10.5281/zenodo.XXXXXXX},
  url = {https://doi.org/10.5281/zenodo.XXXXXXX}
}
```

---

## 🎯 Zenodo 优势

| 优势 | 说明 |
|------|------|
| **正式 DOI** | 可正式引用，永久有效 |
| **永久存储** | CERN 运营，保证长期保存 |
| **免费** | 完全免费，无隐藏费用 |
| **自动更新** | GitHub release 自动同步 |
| **学术认可** | 学术界广泛认可 |
| **开放获取** | 全球免费访问 |
| **版本管理** | 支持多版本，每个版本独立 DOI |

---

## 📈 与 GitHub 集成效果

```
GitHub Release → Zenodo DOI → 正式引用
     ↓              ↓            ↓
  代码托管       学术存储      论文引用
```

**工作流**：
1. GitHub 更新代码/论文
2. 创建新的 release
3. Zenodo 自动创建新版本 DOI
4. 研究者引用最新 DOI

---

## ⚠️ 注意事项

### 许可证选择

**推荐**：CC BY 4.0（知识共享）

| 许可证 | 说明 | 推荐度 |
|--------|------|--------|
| CC BY 4.0 | 允许分享和改编，需署名 | ⭐⭐⭐⭐⭐ |
| CC BY-SA 4.0 | 同上，但衍生作品需同样许可 | ⭐⭐⭐⭐ |
| CC BY-NC 4.0 | 同上，但禁止商业用途 | ⭐⭐⭐ |
| MIT | 软件许可证，不适合论文 | ⭐⭐ |

### 作者信息

- 可使用真实姓名或笔名
- 建议关联 ORCID（可选）
- 机构信息可选填

### 内容要求

- ✅ 学术论文、预印本
- ✅ 代码、数据
- ✅ 演示、报告
- ❌ 侵权内容
- ❌ 非学术内容

---

## 📞 需要您做的

| 步骤 | 操作 | 时间 |
|------|------|------|
| 1 | 注册 Zenodo 账号（GitHub 登录） | 3 分钟 |
| 2 | 启用 GitHub 集成 | 2 分钟 |
| 3 | 创建 GitHub Release v1.0 | 5 分钟 |
| 4 | 完善 Zenodo 记录 | 5 分钟 |
| 5 | 发布获取 DOI | 自动 |
| **总计** | | **15 分钟** |

---

## 🔗 相关链接

- **Zenodo 官网**：https://zenodo.org
- **GitHub 集成**：https://zenodo.org/account/settings/github/
- **使用指南**：https://help.zenodo.org/
- **FAQ**：https://zenodo.org/faq

---

## 📊 发布后效果

**获得**：
- ✅ 正式 DOI（可引用）
- ✅ 永久存储
- ✅ 学术认可
- ✅ 开放获取
- ✅ 版本管理

**论文引用方式**：
```
Zhi, [Name], & Xiao, Zhi 2nd. (2026). Vision-Language-Action Models 
for Embodied AI: A Comprehensive Survey and Research Agenda (v1.0) 
[Data set]. Zenodo. https://doi.org/10.5281/zenodo.XXXXXXX
```

---

**准备状态**：100% 完成  
**待执行**：Zenodo 账号创建、GitHub Release、DOI 获取  
**预计时间**：15 分钟

---

**最后更新**：2026-03-06 20:15  
**维护者**：小志 2 号（AI 科研助手）
