# F1 Race Hub v1

A free, independent, mobile-first PWA for iPhone, in Simplified Chinese with all scheduled event times converted to Malaysia Time (Asia/Kuala_Lumpur).

## Features
- F1 schedule including practice, qualifying, sprint and race sessions, and per-session downloadable iCalendar reminders (60 minutes prior)
- Drivers and constructors standings, with season selection
- OpenF1 historical session data (2023+): final timing position snapshots, latest recorded laps, pit events, tyre compound and race control
- Historical race results and links to reputable F1 news sources
- Installable as a Home Screen web app from HTTPS hosting, with offline caching of the application shell (not API data)

## Deployment on GitHub Pages (free)
1. Create a public GitHub repository named `f1-race-hub`.
2. Upload `index.html`, `styles.css`, `app.js`, `icon.svg`, `manifest.webmanifest`, and `sw.js` into the repository root.
3. In the repository go to Settings → Pages → Build and deployment, select **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
4. Visit `https://YOUR_USERNAME.github.io/f1-race-hub/` in Safari on iPhone. Use Share → Add to Home Screen.
5. Allow network access for data loading. No paid hosting or subscription is required.

`index.html` can be previewed offline, but cross-origin API access may be restricted under the `file://` scheme. Deploy to HTTPS for reliable use.

## Data & caveats
- Jolpica API https://api.jolpi.ca/ergast/f1/; schedule and standing data may not be instantly updated.
- OpenF1 API https://openf1.org/docs/ historical data (since 2023) is free. Its live data during sessions requires a paid subscription.
- No live timing is claimed. Final position and latest interval/lap records are derived from historical session events and may be incomplete.
- News tab links to original sources; there is no automatic news ingestion or push notification service.
- Calendar reminders are downloaded .ics events; iOS import behavior depends on the OS and installed apps. These are not remotely synced if event times change.
- Fan-built and unaffiliated with F1 or the FIA. Review API terms before commercial usage.


## v2：个性化关注
- 在积分榜点击「关注」车手或车队；或在「关注」页手动添加名称。
- 将关注列表及提醒类型偏好存入当前设备 localStorage，不上传服务器。
- 为每个关注对象生成 Google News 最新新闻搜索入口；点开后获取当时可用的新闻结果。
- **目前没有后台新闻采集或系统推送**，设置提醒偏好不代表通知已开启。
- 真正关闭 App 后仍收到 iPhone 通知，需要推送订阅存储、后台采集及 Web Push 服务器，且用户需将 PWA 添加到主屏幕并授权通知。GitHub Pages 本身无法执行此后台工作。
- OpenF1 免费数据不提供比赛期间实时计时，相关数据不可直接作为免费即时赛事通知。
