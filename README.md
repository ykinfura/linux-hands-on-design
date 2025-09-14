# インフラ設計・構築ポートフォリオ

このリポジトリは、Linux サーバー設計・構築の学習環境を基にした成果物をまとめたポートフォリオです。  
VirtualBox 上で Rocky Linux 9 を使用し、**Web + DB システム構成** を再現しました。

---

## 📂 含まれる成果物
- [運用設計書] (./docs/運用設計書.pdf)

- 構築手順書　
[Step1 基盤構築手順書] (./docs/Step1 基盤構築手順書.pdf)
[Step2 OS初期設定 （RockyLinux 9）](./docs/Step2 OS初期設定.pdf)
[Step3 Webサーバー構築 (Nginx)] (./docs/Step3 Webサーバー構築 (Nginx).pdf)
[Step4 DBサーバー構築 (MariaDB)](./docs/Step4 DBサーバー構築 (MariaDB).pdf)
[Step5 Webアプリ構築（AppServer）](./docs/Step5 Webアプリ構築（AppServer）.pdf)
[Step6 運用・監視・バックアップ・セキュリティ強化](./docs/Step6 運用・監視・バックアップ・セキュリティ強化.pdf)

- システム構成図（テキスト & スクリーンショット）

---

## ⚙️ 技術スタック
- OS: Rocky Linux 9
- Web: Nginx / PHP-FPM
- DB: MariaDB
- Security: firewalld / SELinux / fail2ban
- Tools: VirtualBox / GitHub

---

## 🔒 運用設計のポイント
- 監視: cronスクリプトによる死活監視（5分間隔）
- バックアップ: mysqldump によるDBバックアップ（14日保持）
- ログ管理: logrotate による日次ローテーション（14世代）
- セキュリティ: SSH鍵認証、SELinux Enforcing、Firewall最小化
- 障害対応: 軽度＝サービス再起動、重度＝バックアップからリストア

---

## 🖼️ システム構成図
HostPC (Windows)
│ 8080→80 / 2221→22 / 2222→22
▼
AppServer (Nginx/PHP) -- Host-Only -- DBServer (MariaDB)

![構成図](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/構成図.png)

---

## 📑 使用方法
1. `構築手順書.pptx` を参照し VirtualBox で環境を構築  
2. `運用設計書.pptx` を参照し、監視・バックアップ・運用設計を確認  

---

## 👤 作者
- インフラエンジニア  
- 経験: Linuxサーバーキッティング / ネットワーク機器検査  
- 資格: LinuC Lv3(304) / CCNA / AWS SAA（SAP受験予定）/ 基本情報技術者試験
