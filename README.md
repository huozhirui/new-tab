# Tab Out

**A calm new-tab dashboard for cleaning up browser clutter.**

Tab Out replaces Chrome's new tab page with a local dashboard of your open tabs, grouped by domain and organized for fast cleanup. It helps you jump back to the right page, close noisy tab groups, save links for later, and keep a lightweight TODO list next to your browsing context.

No server. No account. No tracking. Everything runs inside the Chrome extension.

## Highlights

- **Open tabs grouped by domain** so you can scan everything you have open at once.
- **Homepages group** pulls common landing pages like Gmail, X, YouTube, LinkedIn, and GitHub into one cleanup-friendly card.
- **Duplicate detection** marks repeated URLs with count badges and closes extras in one click.
- **Cross-window tab switching** lets you click any tab title and jump directly to it.
- **One-click tab cleanup** closes a single tab, a whole domain group, duplicate tabs, or all visible tabs.
- **Save for Later** stores individual tabs in a local checklist before you close them.
- **Archive and search saved items** after marking saved tabs as done.
- **Quick Access** keeps your favorite links on the dashboard, with add, edit, delete, and drag-to-reorder controls.
- **TODO List** supports objectives with optional sub-items, editing, completion, and local persistence.
- **Customizable dashboard order** moves Quick Access, TODO, and Open Tabs sections up or down.
- **Search open tabs** by title, URL, or domain.
- **Toolbar badge** shows the current web-tab count with green, amber, and red workload colors.
- **Swoosh + confetti feedback** makes closing tabs feel deliberate and satisfying.
- **100% local storage** via `chrome.storage.local`; no browsing data is sent anywhere.

## Install

1. Clone the repo:

```bash
git clone https://github.com/huozhirui/new-tab.git
cd new-tab
```

2. Open Chrome's extension manager:

```bash
open "chrome://extensions"
```

3. Enable **Developer mode** in the top-right corner.
4. Click **Load unpacked**.
5. Select the `extension/` folder in this repo.
6. Open a new tab.

Tab Out is a pure Chrome extension, so there is no `npm install`, build step, server, or database to run.

## How To Use

Open a new tab and use the dashboard directly:

- Click a tab title to focus that tab, even if it is in another Chrome window.
- Click the close button beside a tab to close only that page.
- Click **Close all N tabs** on a domain card to close that whole group.
- Click **Close duplicates** when a card shows repeated pages.
- Click the bookmark action on a tab to move it into **Save for Later** before closing.
- Check saved items off when finished; they move into the archive.
- Add common sites to **Quick Access** and drag them into your preferred order.
- Add TODO items and optional sub-items for lightweight task tracking.
- Use section arrows to reorder the dashboard blocks.

## Privacy

Tab Out only uses Chrome extension APIs:

- `chrome.tabs` reads and manages open tabs.
- `chrome.storage.local` stores saved tabs, quick links, TODO items, collapsed states, and dashboard order.
- `chrome.action` updates the toolbar badge.

There are no accounts, remote servers, analytics, or external API calls.

## Optional Local Configuration

If you want personal grouping rules without committing them, create `extension/config.local.js`. The app loads it when present and continues normally when it does not exist.

Example uses:

- Add custom homepage patterns.
- Define custom tab groups for internal tools or project domains.

Keep this file local if it contains private URLs.

## Tech Stack

| Area | Implementation |
| --- | --- |
| Extension platform | Chrome Manifest V3 |
| New tab override | `chrome_url_overrides.newtab` |
| Tab management | `chrome.tabs` |
| Persistence | `chrome.storage.local` |
| Badge | `chrome.action` |
| Sound | Web Audio API |
| Animation | CSS transitions + JavaScript confetti particles |

## Update

```bash
git pull
```

Then open `chrome://extensions` and click the reload button on the extension card.

## License

MIT

---

# 中文说明

**Tab Out 是一个帮你整理浏览器标签页的新标签页仪表盘。**

它会替换 Chrome 默认新标签页，把当前打开的页面按域名分组展示，让你更快找到页面、关闭成组标签、清理重复页面，并把暂时不想处理的链接保存到本地清单。

没有服务器、没有账号、没有追踪。所有数据都保存在本机 Chrome 扩展里。

## 功能亮点

- **按域名分组当前标签页**，一眼看清现在打开了什么。
- **常用首页分组**，把 Gmail、X、YouTube、LinkedIn、GitHub 等首页聚合到一个卡片里。
- **重复标签检测**，重复 URL 会显示数量标记，并支持一键只保留一份。
- **跨窗口跳转标签**，点击标题即可切换到对应页面。
- **快速关闭标签**，支持关闭单个标签、整个域名分组、重复标签或全部当前标签。
- **稍后处理**，关闭前可把单个标签保存到本地清单。
- **归档和搜索**，完成后的稍后处理项会进入归档，并可搜索。
- **快捷访问**，支持添加、编辑、删除常用链接，也可以拖拽排序。
- **TODO List**，支持事项、子项、编辑和完成状态。
- **仪表盘区块排序**，快捷访问、TODO、当前标签三个区块可上下移动。
- **当前标签搜索**，可按标题、链接或域名查找。
- **工具栏徽标**，显示当前真实网页标签数量，并用绿色、橙色、红色表示压力等级。
- **关闭反馈**，关闭标签时有 swoosh 音效和 confetti 动画。
- **100% 本地存储**，使用 `chrome.storage.local`，不会把浏览数据发送到任何地方。

## 安装

1. 克隆仓库：

```bash
git clone https://github.com/huozhirui/new-tab.git
cd new-tab
```

2. 打开 Chrome 扩展管理页：

```bash
open "chrome://extensions"
```

3. 打开右上角 **Developer mode / 开发者模式**。
4. 点击 **Load unpacked / 加载已解压的扩展程序**。
5. 选择本仓库里的 `extension/` 文件夹。
6. 打开一个新标签页即可使用。

Tab Out 是纯 Chrome 扩展，不需要 `npm install`，不需要构建，也不需要启动服务器或数据库。

## 使用方式

- 点击标签标题，直接跳到对应 Chrome 标签页。
- 点击单个标签旁的关闭按钮，只关闭这一页。
- 点击域名卡片上的 **Close all N tabs**，关闭整组标签。
- 出现重复标记时，点击 **Close duplicates** 清理重复页。
- 点击标签的书签按钮，把它加入 **稍后处理** 后再关闭。
- 勾选稍后处理项后，它会进入归档。
- 在 **快捷访问** 中添加常用网站，并拖拽调整顺序。
- 在 **TODO List** 中添加事项和子项。
- 使用区块上下箭头调整仪表盘布局顺序。

## 隐私

Tab Out 只使用 Chrome 扩展 API：

- `chrome.tabs`：读取和管理当前打开的标签页。
- `chrome.storage.local`：保存稍后处理、快捷访问、TODO、折叠状态和区块顺序。
- `chrome.action`：更新工具栏徽标。

没有账号、没有远程服务器、没有分析统计，也不会调用外部 API。

## 可选本地配置

如果你想添加个人分组规则，可以创建 `extension/config.local.js`。文件存在时会自动加载，不存在也不会影响使用。

可以用来：

- 增加自定义首页规则。
- 为内部工具或项目域名定义自定义分组。

如果里面包含私有 URL，建议只保存在本地。

## 更新

```bash
git pull
```

然后打开 `chrome://extensions`，点击扩展卡片上的重新加载按钮。
