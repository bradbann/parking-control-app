# 停车控制系统

安全、高效、可定制的智慧停车解决方案，全套开源

## 本项目一共分为 3 端

1. 服务端 https://github.com/ddhmit/parking-control-server
2. APP 端 https://github.com/ddhmit/parking-control-app
3. 管理端 https://github.com/ddhmit/parking-control-admin

## 特性

1. ⛲ 科学计费 多种计费方案灵活切换，商场、小区、停车场等场景均适用
2. ⏲ 商户放行 配套商户 APP 可由商户控制经停车辆放行，加强市场安全
3. ♉ 无人值守 云端控制实现无岗亭模式下的车辆自主进出，降低人工成本
4. ⛳ 应急开闸 在意外突发情况下，管理员无需到场可随时远程进行开闸放行
5. 🍓 强兼容性 不更换原有抓拍机，可兼容市面上 90%的抓拍机品牌
6. 📱 移动支付 直接使用微信支付宝等扫码支付，无需人工干预提升效率
7. 🎫 电子小票 三轮车等无牌车可采用领取小票方式入场，全流程无缝衔接
8. ⏳ 经停追踪 搭配商户 APP，可随时调阅车辆经停记录，确保装卸货万无一失
9. 🙋 人像识别 智能人像识别系统，确保小区业主通行无阻，保障小区安全

## 技术架构

该系统服务端理论上兼容全平台，目前我们在生产环境中是在 ubuntu 上使用 docker 部署的
该套系统采用 web 全栈解决方案，服务端 node.js，APP ionic，管理端 react
但还包括 docker，eggjs，redis，mongodb，socket.io，微信支付等技术细节

## 使用

### 服务端部署方法

1. ubuntu `cd ../srv`
2. ubuntu `git clone https://github.com/ddhmit/parking-control-server.git`
3. ubuntu `docker network create net-1`
4. ubuntu `docker run -ti -p 7002:7002 --name parkserver --network net-1 --network-alias parkserver --restart always -v /srv/parking-control-server:/srv/parking-control-server -v /logs:/root/logs -v /etc/localtime:/etc/localtime:ro --privileged=true -d node sh -c 'cd /srv/parking-control-server && npm i && npm run start'`

### 前端及 APP 打包部署

1. `npm i`
2. `npm run build`
