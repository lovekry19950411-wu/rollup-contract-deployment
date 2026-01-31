📘 Counter Project Master
專案簡介
本專案示範如何在 Rollup 網路上部署智慧合約，並提供基礎範例以驗證合約的正確性與可用性。

目前包含兩部分：
- HelloWorld 合約：簡單訊息儲存與更新，作為基礎部署範例。
- Counter 合約：計數器功能，展示合約狀態的更新與事件觸發。
🔜 後續規劃：將延伸至 NFT 合約，支援 metadata 與圖片整合，並搭配前端介面進行展示。

專案結構
counter-project-master/
├── contracts/          # 智慧合約 (HelloWorld.sol) 

├── src/                # NFT/Counter 合約 (Counter.sol)

├── deployments/        # 部署腳本 (deploy.js)

├── metadata/           # NFT metadata JSON (0.json, 1.json)

├── lib/                # 外部依賴 (forge-std, openzeppelin-contracts)

├── token-api-script.js # API 與部署輔助腳本

├── hardhat.config.js   # Hardhat 設定檔

├── foundry.lock        # Foundry 鎖定檔

├── package.json        # NPM 設定

├── .gitignore          # 忽略檔案設定

└── README.md           # 專案說明文件

前置需求
- Node.js & NPM
- Hardhat / Foundry
- Metamask 錢包
- Alchemy RPC URL
- 已完成官方教學：
- 將 rollup 加入錢包
- 橋接母鏈資金到 rollup
- 取得測試代幣

安裝步驟
# 安裝依賴
npm install

# 編譯合約
npx hardhat compile

# 部署 HelloWorld 合約
npx hardhat run deployments/deploy.js --network rollup

測試
npx hardhat test

範例測試檔 (test/HelloWorld.js) 
驗證合約能正確更新訊息並觸發事件。

.gitignore
node_modules/
artifacts/
cache/
out/
broadcast/
.env

後續規劃
- 完成 NFT 圖片上傳與 metadata 整合
- 建立前端介面 (React/Next.js) 與合約互動
- 擴展為完整 dApp，支援更多商業邏輯
