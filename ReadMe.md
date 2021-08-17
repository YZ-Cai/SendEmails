# 使用Python群发邮件

通过Python群发相同内容的邮件给不同收件人，支持纯文本（text）与富文本（html）两种内容形式。

若需要为不同的收件人定制不同的邮件内容，或者需要添加附件，请参考https://www.runoob.com/python/python-email.html

<br/>

## 0 文件说明

- SendEmails.py：Python代码文件
- EmailReceiversList.csv：邮件接收者列表
- EmailContent.txt：纯文本邮件内容，无格式
- EmailContent.html：富文本形式邮件内容，可自行编辑带格式内容
- FailList.csv：发送失败的邮箱列表

<br/>

## 1 准备工作

安装所需包

```
pip install PyEmail 
```

```
pip install emails
```

关于smtplib包的说明请参考：https://blog.csdn.net/qq_40833182/article/details/82504163

<br/>

## 2 代码内相关参数

### 2.1 发件邮箱设置

包括邮箱账号、密码、昵称，以及发件邮箱的SMTP地址与端口。

```python
emailSender = 'xxx@xxx'       # 发件人邮箱账号
emailSenderPassword = 'xxx'   # 发件人邮箱密码
emailSenderName = "昵称"      # 发件人昵称
emailSMTPAddress = "xxxx"     # 发件人邮箱SMTP地址（一般为smtp.邮箱后缀，如smtp.126.com）
emailSMTPPort = 25            # 发件人邮箱SMTP端口（非加密端口一般为25，加密端口一般为465）
```

SMTP地址一般为“smtp.邮箱后缀”，如邮箱为“xxx@126.com”时SMTP地址为“smtp.126.com”。SMTP非加密端口一般为25，加密端口一般为465，常用邮箱端口可参考https://blog.csdn.net/ning521513/article/details/79217203

### 2.2 邮件设置

可设置邮件主题（标题）与邮件内容。

```python
emailTitle = "测试标题"                       # 邮件主题（标题）
emailContentFilename = "EmailContent.txt"     # 邮件内容（文本形式）
#emailContentFilename = "EmailContent.html"   # 邮件内容（富文本形式）
```

若想使用纯文本形式，可将文本放置于EmailContent.txt文件内，并在代码中注释掉html文件名所在行；若想使用富文本html格式，可编辑EmailContent.html文件，并在代码中注释掉txt文件名所在行。此处默认是纯文本格式。

### 2.3 收件人列表

请将所有收件人的邮箱放置于EmailReceiversList.csv文件中，每行一个。

<br/>

## 3 代码运行

运行Python代码输出

```
成功发送邮件至：xxx@xxx
成功发送邮件至：xxx@xxx
成功发送邮件至：xxx@xxx
尝试发送至yyy@yyy失败
成功发送邮件至：xxx@xxx
共有4封邮件发送成功，1封邮件发送失败
```

若存在邮件发送失败，会被存至FailList.csv文件中

<br/>

## 4 更多功能

若需要为不同的收件人定制不同的邮件内容，或者需要添加附件，请参考https://www.runoob.com/python/python-email.html