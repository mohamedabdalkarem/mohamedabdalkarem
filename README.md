<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>GitHub Hero</title>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600&family=Syne:wght@400;700;800&display=swap" rel="stylesheet"/>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { background: #060a14; display: flex; justify-content: center; align-items: center; min-height: 100vh; }

    .hero-wrap {
      font-family: 'Syne', sans-serif;
      background: #0a0e1a;
      border-radius: 12px;
      overflow: hidden;
      position: relative;
      width: 700px;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .grid-bg {
      position: absolute;
      inset: 0;
      background-image:
        linear-gradient(rgba(55, 138, 221, 0.07) 1px, transparent 1px),
        linear-gradient(90deg, rgba(55, 138, 221, 0.07) 1px, transparent 1px);
      background-size: 36px 36px;
      pointer-events: none;
    }

    .glow-orb {
      position: absolute;
      width: 320px;
      height: 320px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(24, 95, 165, 0.22) 0%, transparent 70%);
      top: -80px;
      right: -40px;
      pointer-events: none;
    }

    .glow-orb2 {
      position: absolute;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      background: radial-gradient(circle, rgba(29, 158, 117, 0.14) 0%, transparent 70%);
      bottom: -60px;
      left: 60px;
      pointer-events: none;
    }

    .content {
      position: relative;
      z-index: 2;
      padding: 2.5rem 2.5rem 2rem;
    }

    .eyebrow {
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      color: #378ADD;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 0.75rem;
      display: flex;
      align-items: center;
      gap: 8px;
      opacity: 0;
      animation: fadeUp 0.5s ease 0.1s forwards;
    }

    .eyebrow::before {
      content: '';
      width: 20px;
      height: 1px;
      background: #378ADD;
    }

    .name {
      font-size: 42px;
      font-weight: 800;
      color: #f0f4ff;
      line-height: 1.05;
      margin: 0 0 0.5rem;
      letter-spacing: -0.02em;
      opacity: 0;
      animation: fadeUp 0.5s ease 0.2s forwards;
    }

    .name span { color: #378ADD; }

    .tagline-row {
      font-family: 'JetBrains Mono', monospace;
      font-size: 13px;
      color: #5DCAA5;
      margin-bottom: 1.75rem;
      display: flex;
      align-items: center;
      gap: 6px;
      opacity: 0;
      animation: fadeUp 0.5s ease 0.3s forwards;
    }

    .cursor {
      display: inline-block;
      width: 8px;
      height: 14px;
      background: #5DCAA5;
      vertical-align: middle;
      animation: blink 1s step-end infinite;
    }

    .tags-row {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      opacity: 0;
      animation: fadeUp 0.5s ease 0.45s forwards;
    }

    .tag {
      font-family: 'JetBrains Mono', monospace;
      font-size: 11px;
      font-weight: 600;
      padding: 5px 12px;
      border-radius: 4px;
      letter-spacing: 0.04em;
    }

    .tag-blue {
      background: rgba(55, 138, 221, 0.15);
      color: #85B7EB;
      border: 0.5px solid rgba(55, 138, 221, 0.35);
    }

    .tag-green {
      background: rgba(29, 158, 117, 0.15);
      color: #5DCAA5;
      border: 0.5px solid rgba(29, 158, 117, 0.35);
    }

    .tag-amber {
      background: rgba(186, 117, 23, 0.15);
      color: #FAC775;
      border: 0.5px solid rgba(186, 117, 23, 0.3);
    }

    .stats-strip {
      position: relative;
      z-index: 2;
      display: flex;
      border-top: 0.5px solid rgba(55, 138, 221, 0.15);
      opacity: 0;
      animation: fadeUp 0.5s ease 0.6s forwards;
    }

    .stat {
      flex: 1;
      padding: 0.9rem 1.5rem;
      border-right: 0.5px solid rgba(55, 138, 221, 0.12);
    }

    .stat:last-child { border-right: none; }

    .stat-val {
      font-family: 'Syne', sans-serif;
      font-weight: 700;
      font-size: 18px;
      color: #f0f4ff;
      line-height: 1;
    }

    .stat-label {
      font-family: 'JetBrains Mono', monospace;
      font-size: 10px;
      color: rgba(176, 196, 230, 0.5);
      margin-top: 3px;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    .divider {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: 2px;
      background: linear-gradient(90deg, transparent, #185FA5 40%, #0F6E56 70%, transparent);
      opacity: 0.6;
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(10px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    @keyframes blink {
      0%, 100% { opacity: 1; }
      50%       { opacity: 0; }
    }
  </style>
</head>
<body>

  <div class="hero-wrap">
    <div class="grid-bg"></div>
    <div class="glow-orb"></div>
    <div class="glow-orb2"></div>

    <div class="content">
      <div class="eyebrow">mohamedabdalkarem / README.md</div>
      <h1 class="name">Mohamed <span>Abdelkareem</span></h1>
      <div class="tagline-row">
        &gt;&nbsp;engineering data pipelines<span class="cursor"></span>
      </div>
      <div class="tags-row">
        <span class="tag tag-blue">Data Engineering</span>
        <span class="tag tag-green">Modeling</span>
        <span class="tag tag-amber">Big Data</span>
        <span class="tag tag-blue">Entrepreneur</span>
      </div>
    </div>

    <div class="stats-strip">
      <div class="stat">
        <div class="stat-val">Data Engineer</div>
        <div class="stat-label">role</div>
      </div>
    </div>

    <div class="divider"></div>
  </div>

</body>
</html>
&nbsp;

[![Data Engineering](https://img.shields.io/badge/Data_Engineering-0c1e3e?style=flat-square&logoColor=60a5fa)](.)
[![Modeling](https://img.shields.io/badge/Modeling-052010?style=flat-square&logoColor=60a5fa)](.)
[![Big Data](https://img.shields.io/badge/Big_Data-1a1000?style=flat-square&logoColor=60a5fa)](.)
</div>

---

🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Languages** | ![Python](https://img.shields.io/badge/Python-%23060810?style=flat-square&logo=python&logoColor=3572a5) ![SQL](https://img.shields.io/badge/SQL-%23060810?style=flat-square&logo=postgresql&logoColor=e38c28) ![Bash](https://img.shields.io/badge/Bash-%23060810?style=flat-square&logo=gnubash&logoColor=64748b) |
| **Big Data** | ![Spark](https://img.shields.io/badge/Apache_Spark-%23060810?style=flat-square&logo=apachespark&logoColor=e25a1c) ![Hadoop](https://img.shields.io/badge/Hadoop-%23060810?style=flat-square&logo=apachehadoop&logoColor=fbbf24) ![Hive](https://img.shields.io/badge/Hive-%23060810?style=flat-square&logo=apachehive&logoColor=34d399) ![Kafka](https://img.shields.io/badge/Kafka-%23060810?style=flat-square&logo=apachekafka&logoColor=94a3b8) |
| **DevOps** | ![Docker](https://img.shields.io/badge/Docker-%23060810?style=flat-square&logo=docker&logoColor=60a5fa) ![Git](https://img.shields.io/badge/Git-%23060810?style=flat-square&logo=git&logoColor=f87171) ![CI/CD](https://img.shields.io/badge/CI%2FCD-%23060810?style=flat-square&logo=githubactions&logoColor=64748b) ![Kubernetes](https://img.shields.io/badge/Kubernetes-%23060810?style=flat-square&logo=kubernetes&logoColor=22d3ee) |
| **Engineering** | ![ETL](https://img.shields.io/badge/ETL%2FELT-%23060810?style=flat-square&logoColor=a78bfa) ![Data Warehouse](https://img.shields.io/badge/Data_Warehouse-%23060810?style=flat-square&logoColor=a78bfa) ![Airflow](https://img.shields.io/badge/Airflow-%23060810?style=flat-square&logo=apacheairflow&logoColor=34d399) ![dbt](https://img.shields.io/badge/dbt-%23060810?style=flat-square&logo=dbt&logoColor=34d399) |
| **Databases** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-%23060810?style=flat-square&logo=postgresql&logoColor=60a5fa) ![MySQL](https://img.shields.io/badge/MySQL-%23060810?style=flat-square&logo=mysql&logoColor=60a5fa) ![HBase](https://img.shields.io/badge/HBase-%23060810?style=flat-square&logoColor=fbbf24) ![Cassandra](https://img.shields.io/badge/Cassandra-%23060810?style=flat-square&logo=apachecassandra&logoColor=f0abfc) ![Redis](https://img.shields.io/badge/Redis-%23060810?style=flat-square&logo=redis&logoColor=f87171) |
| **Cloud** | ![Snowflake](https://img.shields.io/badge/Snowflake-%23060810?style=flat-square&logo=snowflake&logoColor=22d3ee) ![AWS](https://img.shields.io/badge/AWS-%23060810?style=flat-square&logo=amazonaws&logoColor=fbbf24) |

---

📊 GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=mohamedabdalkarem&show_icons=true&theme=github_dark&hide_border=true&bg_color=060810&title_color=3b82f6&icon_color=3b82f6&text_color=64748b&ring_color=1e3a8a" height="155" />
<img src="https://github-readme-streak-stats.herokuapp.com/?user=mohamedabdalkarem&theme=dark&hide_border=true&background=060810&ring=3b82f6&fire=60a5fa&currStreakLabel=3b82f6&sideNums=64748b&sideLabels=334155&dates=334155" height="155" />

</div>

---

🤝 Connect With Me

<div align="center">

[![WhatsApp](https://img.shields.io/badge/WhatsApp-01012390457-%23060810?style=for-the-badge&logo=whatsapp&logoColor=25d366&labelColor=052010)](https://wa.me/201012390457)
[![X / Twitter](https://img.shields.io/badge/X-@Mohammed285239-%23060810?style=for-the-badge&logo=x&logoColor=e7e7e7&labelColor=0a0a10)](https://x.com/Mohammed285239)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-mohammed--abdalkareem-%23060810?style=for-the-badge&logo=linkedin&logoColor=0a66c2&labelColor=0c1e3e)](https://www.linkedin.com/in/mohammed-abdalkareem-26297b236)
[![Email](https://img.shields.io/badge/Email-mohamedabdalkareem976-%23060810?style=for-the-badge&logo=gmail&logoColor=ea4335&labelColor=1a0808)](mailto:mohamedabdalkareem976@gmail.com)

</div>

---

<div align="center">

```
// always building  ·  always learning  ·  always shipping
```

![Profile Views](https://komarev.com/ghpvc/?username=mohamedabdalkarem&color=3b82f6&style=flat-square&label=profile+views)

</div>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:1e3a8a,60:0c1e3e,100:060810&height=80&section=footer" />
