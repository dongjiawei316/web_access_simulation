# web_access_simulation
使用python写的一个模拟访问设备web的程序，希望能够用于自动化测试

1 适用设备
	适用于具有json-rpc协议web的设备
2 自动化测试原理
利用python3的urllib库，模拟http访问设备web，记录每次访问的post内容和设备的响应。
运行的步骤是：
（1）	读入rpc配置文件，为了方便读取，对齐，该文件由一个json字串组成。里面包含了post的json-rpc字串和命令间的间隔信息。
（2）	使用urllib依次将json-rpc字串post到目标设备或者休眠一段时间
（3）	记录post内容和设备反馈
（4）	如果循环次数未到设定值，跳到第二步继续执行，否则结束
3 执行的命令
可以在安装了python3的linux服务器（53.15）上运行脚本：
python3 auto_test.py --ip 192.165.53.161 --file test.rpc --out log1.txt --count 0

如果windows电脑上安装了python3，也可以在命令行下执行
python3 auto_test.py --ip 192.165.53.161 --file test.rpc --out log1.txt --count 0

注意：必须在auto_test.py的路径下执行

也可以用PyCharm来运行的。

