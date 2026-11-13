# z-mobbin-frontend-design

## ✨ 功能概览

- 按用户任务查阅 Mobbin Flows，再用 Screens 补充关键状态。
- 记录产品、原始链接、已看步骤和覆盖范围，区分观察与推断。
- 将参考转化为适合目标产品的设计决策，不假定受限内容已覆盖。
> 功能概览由 [Lobe Readme Wizard](https://github.com/lobehub/lobe-readme-wizard) 的 Markdown 生成器生成，内容依据本仓库资料整理。

为 Web 前端设计与改版调研 Mobbin 案例，将实际看过的产品流程转化成有来源、可追溯的设计决策。

## 适用场景

适合设计师、产品经理与开发者研究任务列表、详情页和其他 Web 用户流程。输入是用户任务、现有行为和希望研究的状态；输出是案例证据、覆盖范围、观察和设计建议。`z-` 是个人命名前缀，不是官方要求。

## 前置条件

- Codex 可使用 Chrome 和 Computer Use，并能访问已登录 Mobbin 的 Chrome 浏览器配置。
- Mobbin 账户可访问相应内容；Pro 内容需相应访问权限。本技能不绕过网站权限或要求使用 MCP。
- 客户端需能操作真实浏览器；权限和访问范围由所在环境决定。

## 安装到 Codex

在终端执行；如果目标已存在（包括软链接）会停止，避免覆盖已有技能：

```sh
git clone https://github.com/score2021/z-mobbin-frontend-design.git
cd z-mobbin-frontend-design
skill_dest="$HOME/.agents/skills/z-mobbin-frontend-design"
if [ -e "$skill_dest" ] || [ -L "$skill_dest" ]; then
  printf '%s\n' "目标已存在，未安装：$skill_dest" >&2
else
  mkdir -p "$HOME/.agents/skills"
  mkdir "$skill_dest"
  cp SKILL.md "$skill_dest/SKILL.md"
  printf '%s\n' "已安装：$skill_dest"
fi
```

开始新会话后用 `$z-mobbin-frontend-design` 调用；若未出现在列表中，请重新打开客户端。不要同时安装同名副本。其他客户端尚未验证。

## 样例

在 Codex 对话中发送：

```text
$z-mobbin-frontend-design 请调研 Web 任务管理台的任务列表到详情流程。
用户希望看到当前状态、等待澄清和失败后的下一步；现有创建与详情功能必须保留。
找 2–3 个产品，先逐步看 Flows，再用 Screens 补查失败与空状态。
给出原始链接、实际看过的步骤、观察到的交互和借鉴点；只输出调研，不改代码。
```

需要满足上面的浏览器与账户前置条件。预期在对话中得到带覆盖说明的证据表，不保存文件，除非另有要求。

## 成果展示

以下是**未执行示意**，展示输出形式，并非某个产品的实际观察：

| 参考覆盖 | 实际观察 | 可能借鉴 |
| --- | --- | --- |
| 某 Web 产品的任务详情：部分步骤 | 已看到任务状态和错误提示，未看到失败后的恢复 | 在详情页靠近状态处展示下一步；恢复交互仍需验证 |

真实调研须替换为实际产品与原始链接，区分现场观察和设计推断；无法访问的步骤不得标为已完成。

## 工作方式和边界

优先逐步浏览 Flows，再用 Screens 补充关键状态；逐项标注完整流程、部分步骤或单屏。Pro 内容没有显示时，先等待加载，再关闭当前标签并重新打开原链接一次；仍不可访问就如实记录。只调研、原型或实现，依用户要求确定，不自动发布。

## 验证与来源

技能基于对 Mobbin 官网浏览流程的整理，不包含 Mobbin 截图、付费素材或账户信息。本仓库的浏览器行为依赖账户与工具环境；重命名后真实客户端的独立行为验收请以实际结果为准。仓库未指定开源许可证。

## 文件

- `SKILL.md`：技能入口和工作流程。
- `README.md`：安装和使用说明。
