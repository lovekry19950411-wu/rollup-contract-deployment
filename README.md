📘 Counter Project Master
專案簡介
本專案示範如何在 Rollup 網路上部署智慧合約，並延伸至 NFT 合約。
目前包含兩部分：
- HelloWorld 合約：簡單訊息儲存與更新。
- Counter/NFT 合約：可生成 NFT，並支援 metadata 與圖片擴充。
專案結構
counter-project-master/
│── contracts/          # 智慧合約 (HelloWorld.sol)
│── src/                # NFT/Counter 合約 (Counter.sol)
│── deployments/        # 部署腳本 (deploy.js)
│── metadata/           # NFT metadata JSON (0.json, 1.json)
│── lib/                # 外部依賴 (forge-std, openzeppelin-contracts)
│── token-api-script.js # API 與部署輔助腳本
│── hardhat.config.js   # Hardhat 設定檔
│── foundry.lock        # Foundry 鎖定檔
│── package.json        # NPM 設定
│── .gitignore          # 忽略檔案設定
│── README.md           # 專案說明文件


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


範例測試檔 (test/HelloWorld.js) 驗證合約能正確更新訊息並觸發事件。
NFT 部分
- NFT metadata JSON 範例：
{
  "name": "My Ship NFT",
  "description": "A unique ship NFT",
  "image": "ipfs://<你的圖片CID>"
}


- 後續可將圖片上傳至 IPFS/Pinata，並更新 tokenURI 指向 metadata。
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
