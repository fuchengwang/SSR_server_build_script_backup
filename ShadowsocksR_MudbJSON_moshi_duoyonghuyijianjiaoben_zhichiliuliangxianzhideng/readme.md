vultr账号注册链接： https://www.vultr.com/?ref=7224941

本脚本需要Linux root账户权限才能正常安装运行，所以如果不是 root账号，请先切换为root，如果是 root账号，那么请跳过！

sudo su
输入上面代码回车后会提示你输入当前用户的密码，输入并回车后，没有报错就继续下面的步骤安装ShadowsocksR。

注意：如果你安装的有我的另一个 ssr.sh 脚本，请先卸载ShadowsocksR服务端，再安装这个脚本（不能共存）！

wget -N --no-check-certificate https://github.com/Turing2333/SSR_server_build_script_backup/blob/master/ShadowsocksR_MudbJSON_moshi_duoyonghuyijianjiaoben_zhichiliuliangxianzhideng/ssrmu.sh

注意：关于限制设备数数，这个协议必须是非原版并且不兼容原版才有效，也就是必须SSR客户端使用协议的情况下，才有效！

使用说明

运行脚本，

bash ssrmu.sh
 
# 还有一个 运行参数，是用于所有用户流量清零的
bash ssrmu.sh clearall
# 不过不需要管这个，可以通过脚本自动化的设置 crontab 定时运行脚本
输入对应的数字来执行相应的命令。

  ShadowsocksR MuJSON一键管理脚本 [vX.X.X]
  ---- Toyo | doub.io/ss-jc60 ----
 
  1. 安装 ShadowsocksR
  2. 更新 ShadowsocksR
  3. 卸载 ShadowsocksR
  4. 安装 libsodium(chacha20)
————————————
  5. 查看 账号信息
  6. 显示 连接信息
  7. 设置 用户配置
  8. 手动 修改配置
  9. 清零 已用流量
————————————
 10. 启动 ShadowsocksR
 11. 停止 ShadowsocksR
 12. 重启 ShadowsocksR
 13. 查看 ShadowsocksR 日志
————————————
 14. 其他功能
 15. 升级脚本
 
 当前状态: 已安装 并 已启动
 
请输入数字 [1-15]：
注意：添加/删除/修改 用户配置后，无需重启ShadowsocksR服务端，ShadowsocksR服务端会定时读取数据库文件内的信息，不过修改 用户配置后，可能要等个十几秒才能应用最新的配置（因为ShadowsocksR不是实时读取数据库的，所以有间隔时间）。
文件位置

安装目录：/usr/local/shadowsocksr

配置文件：/usr/local/shadowsocksr/user-config.json

数据文件：/usr/local/shadowsocksr/mudb.json

注意：ShadowsocksR服务端不会实时的把流量数据写入 数据库文件，所以脚本读取流量信息也不是实时的！
其他说明

ShadowsocksR 安装后，自动设置为 系统服务，所以支持使用服务来启动/停止等操作，同时支持开机启动。

启动 ShadowsocksR：service ssrmu start
停止 ShadowsocksR：service ssrmu stop
重启 ShadowsocksR：service ssrmu restart
查看 ShadowsocksR状态：service ssrmu status
ShadowsocksR 默认支持UDP转发，服务端无需任何设置。

本脚本已经集成了 安装/卸载 锐速(ServerSpeeder)/Lotserver，但是是否支持请查看 Linux支持内核列表 。（锐速、LotServer不支持OpenVZ）

 

注意：本脚本中的 显示链接信息中的 获取IP归属地功能使用的是 IPIP.NET 的免费API接口，因为限速所以每秒只能检测一次，同时 IPIP.NET 的免费API接口并不会保证稳定性，可能什么时候就突然暂时失效了，这是本人不可控的，有条件可以自建API接口。
