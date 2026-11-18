# 学习日志

## 2026-11-18

- **今天做了什么**：走完 W10 三个实验——① 用 `git init` / `add` / `commit` / `push` 把个人项目推上 GitHub（`ydl-creater/board-game-product`）；② 给仓库加最小 Streamlit 复利计算器，本地建 `.venv` 装包验证，用 `python -m pip freeze > requirements.txt` 把依赖清单写全后推上 GitHub；③ 按实验三「无密钥路线」完成部署前检查清单、本地回归验证与收尾。
- **关键决定**：项目目前没用到 tushare / 大模型 API 等密钥，按实验三开头指引跳过第 2、5 节（密钥代码改造与云端 Secrets 配置）。`.env` 只留在本地、永不入库——`.gitignore` 已挡住，`git status` 实测看不到它。将来真要接 AI / 取数时采用「本地 `.env` + 云端 Secrets 双通道」：云端拿不到仓库外的 `.env`，密钥必须由平台 Secrets 单独加密传递；代码用 `get_key()` 兼容写法，一份代码本地读 `.env`、云端读 `st.secrets`。
- **新东西**：git 日常三连（status → add → commit → push）；`push` 后 Streamlit Cloud 会自动重新部署；`pip freeze` 冻结版本号让依赖可复现；Streamlit 的 `AppTest` 可在无浏览器环境下验证应用是否正常。
- **卡点**：建 GitHub 仓库时误勾了 "Add a README file"，云端多出一条自动生成的提交导致 push 被拒；确认远端只有模板内容后，用 `git push --force` 覆盖解决。
- **互助记录**：无。
