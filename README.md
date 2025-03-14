📝 **天翼云盘签到脚本** 🤖✨

---

### 🔑 账号配置 & 环境变量

**路径**：`Settings` → `Secrets and variables` → `Actions` → `Repository secrets`
需新建以下加密变量：


| 变量名🐈             | 说明 📌                                                                                                                                                 | 示例 🖼️                            |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| `TYYS`               | 家庭ID账号密码组，格式：`家庭云ID 账号1 密码1 账号2 密码2 -- 家庭云ID 账号1 密码1 账号2 密码2`                                                       | `FID u1 p1 u2 p2 -- FID u1 p1 u2 p2` |
| `PRIVATE_THREADX`    | 个人云签到线程数（不填默认10）                                                                                                                          | `15`                                 |
| `FAMILY_THREADX`     | 家庭云签到线程数（不填默认10）                                                                                                                          | `8`                                  |
| `PRIVATE_ONLY_FIRST` | 个人云仅签主账号：`true`(是)/`false`(不签)（不填默认false）                                                                                             | `true`                               |
| `WX_PUSHER_UID`      | 推送UID（微信扫码-我的-我的UID）[二维码](https://wxpusher.zjiecode.com/api/qrcode/4Ix7noqD3L7DMBoSlvig3t4hqjFWzPkdHqAYsg8IzkPreW7d8uGUHi9LJO4EcyJg.jpg) | `UID_123`                            |

---

`家庭云ID抓取教程：`[Ailst文档](https://alist.nn.ci/zh/guide/drivers/189.html#%E5%AE%B6%E5%BA%AD%E8%BD%AC%E7%A7%BB)

### 🚀 快速执行指南

1️⃣  **启用Workflow**
✅点击仓库顶部 `Actions` → **`I understand my workflows, go ahead and enable them`** 开启权限

2️⃣  **触发运行**
🌟 啊喂 你都fork了 给仓库点个 **Star** 啊

3️⃣  **定时任务**
⏰ 每天 **北京时间 5:00** 自动执行

---

### 💻 本地调试命令

```bash
git clone https://github.com/zhlhlf/drive_checkin --depth=1

cd drive_checkin && npm install

#账号密码空格隔开每个账号也空格隔开 例：FID u1 p1 u2 p2 u3 p3 -- FID u1 p1 u2 p2
export TYYS=""

# 指定签到的家庭云ID
export TYY_FAMILY_ID=""

# 私有云签到线程数量 默认10
export PRIVATE_THREADX=""

# 每个家庭云签到线程数量 默认10
export FAMILY_THREADX=""

# 个人签到是否只签主账号 true(是)  false为否会签到所有号  默认false
export PRIVATE_ONLY_FIRST=""

#推送相关
export TELEGRAM_CHAT_ID=""
export TELEGRAM_BOT_TOKEN=""
export WX_PUSHER_APP_TOKEN=""
export WX_PUSHER_UID=""
npm run start
```

---

### 🐉 青龙面板部署

```bash
# 订阅链接
ql repo https://github.com/zhlhlf/drive_checkin.git "Cloud189.js" "" ".*" "main" "js | json"

# 依赖安装
    xml2js
    tough-cookie
    node-jsencrypt
    superagent
    log4js

# 配置好上面的环境变量
```

---

🙏 **特别鸣谢**
原项目：[wes-lin/Cloud189Checkin](https://github.com/wes-lin/Cloud189Checkin)

修改README：[ShelbyAlan](https://github.com/ShelbyAlan)💡
