# Ubuntu系统的Python默认版本切换
## 命令
```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python2 100   
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 150  
```
这两条命令在本机设置两个python版本为不同编号，然后便于启动。

## 检查pyhton版本的命令
```
python　--version
```
如果无误，此时python版本应该切换到默认的python3了。

## 切换方法
```
sudo update-alternatives --config python
```
然后选择python版本，输入序号回车即可。
因为系统很多程序依赖于python2，如需要升级系统或者安装系统更新的时候，建议先切换到系统的默认版本python2否则可能出现依赖无法安装问题。  
另外就是yah3c是python2版本的，所以每次开机连网需要切换回python2，源于万恶的校园网。
