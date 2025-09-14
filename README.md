# インフラ設計・構築ポートフォリオ

このリポジトリは、Linux サーバー設計・構築の学習環境を基にした成果物をまとめたポートフォリオです。  
VirtualBox 上で Rocky Linux 9 を使用し、**Web + DB システム構成** を再現しました。

---

## 📂 含まれる成果物
- [運用設計書](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/%E9%81%8B%E7%94%A8%E8%A8%AD%E8%A8%88%E6%9B%B8.pdf)

- 構築手順書　
- [Step1 基盤構築手順書](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/Step1%20%E5%9F%BA%E7%9B%A4%E6%A7%8B%E7%AF%89%E6%89%8B%E9%A0%86%E6%9B%B8.pdf)
- [Step2 OS初期設定 （RockyLinux 9)](https://github.com/ykinfura/linux-hands-ondesign/blob/main/docs/Step2%20OS%E5%88%9D%E6%9C%9F%E8%A8%AD%E5%AE%9A%EF%BC%88RockyLinux%209%EF%BC%89.pdf)
- [Step3 Webサーバー構築 (Nginx)](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/Step3%20Web%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E6%A7%8B%E7%AF%89%20(Nginx).pdf)
- [Step4 DBサーバー構築 (MariaDB)](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/Step4%20DB%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E6%A7%8B%E7%AF%89%20(MariaDB).pdf)
- [Step5 Webアプリ構築（AppServer）](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/Step5%20Web%E3%82%A2%E3%83%97%E3%83%AA%E6%A7%8B%E7%AF%89%EF%BC%88AppServer%EF%BC%89.pdf)  
- [Step6 運用・監視・バックアップ・セキュリティ強化](https://github.com/ykinfura/linux-hands-on-design/blob/main/docs/Step6%20%E9%81%8B%E7%94%A8%E3%83%BB%E7%9B%A3%E8%A6%96%E3%83%BB%E3%83%90%E3%83%83%E3%82%AF%E3%82%A2%E3%83%83%E3%83%97%E3%83%BB%E3%82%BB%E3%82%AD%E3%83%A5%E3%83%AA%E3%83%86%E3%82%A3%E5%BC%B7%E5%8C%96.pdf)

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
1. `構築手順書 Step1～6.pdf` を参照し VirtualBox で環境を構築  
3. `運用設計書.pdf` を参照し、監視・バックアップ・運用設計を確認  

---

## 👤 作者
- インフラエンジニア  
- 経験: Linuxサーバーキッティング / ネットワーク機器検査  
- 資格: LinuC Lv3(304) / CCNA / AWS SAA（SAP受験予定）/ 基本情報技術者試験
