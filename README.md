1、pywin32必须安装225版本：
pip install pywin32==225

2、DLL load failed while importing win32api
(python38) H:\pyscript\stock_analysis\thsauto>python .\server.py  127.0.0.1 5000 D:\同花顺软件\同花顺\xiadan.exe
Traceback (most recent call last):
  File ".\server.py", line 3, in <module>
    from thsauto import ThsAuto
  File "H:\pyscript\stock_analysis\thsauto\thsauto.py", line 1, in <module>
    import win32api
ImportError: DLL load failed while importing win32api: 找不到指定的程序。
  
解决办法：
找到文件pywin32_postinstall.py的路径，
由于安装路径不同，可能位置不一样，可以在你安装python的文件夹搜索这个文件，
一般在安装文件下的Scripts文件里，用cmd进入这个Scripts文件夹：

如cd /d D:\Python\Miniconda3\Scripts
在路径下运行python pywin32_postinstall.py -install
操作完成后就能正常运行了。

# thsauto
同花顺自动下单工具

```
python .\server.py  192.168.0.116 5000 C:\Users\match\Desktop\THS\xiadan.exe
```
- 查询资金账户  
http://192.168.0.116:5000/thsauto/balance  
- 查询持仓  
http://192.168.0.116:5000/thsauto/position  
- 买入下单  
http://192.168.0.116:5000/thsauto/buy?stock_no=600000&price=10.00&amount=100  
- 卖出下单  
http://192.168.0.116:5000/thsauto/sell?stock_no=600000&price=10.00&amount=100  
- 科创板买入下单  
http://192.168.0.116:5000/thsauto/buy/kc?stock_no=688819&price=40.00&amount=200  
- 科创板卖出下单  
http://192.168.0.116:5000/thsauto/sell/kc?stock_no=688819&price=40.00&amount=200  
- 查询未成订单  
http://192.168.0.116:5000/thsauto/orders/active  
- 查询已成订单  
http://192.168.0.116:5000/thsauto/orders/filled  
- 撤单  
http://192.168.0.116:5000/thsauto/cancel?entrust_no=2060704404  
- 关闭同花顺客户端  
http://192.168.0.116:5000/thsauto/client/kill  
- 重启同花顺客户端  
http://192.168.0.116:5000/thsauto/client/restart  
