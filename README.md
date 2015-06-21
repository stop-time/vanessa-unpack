# Yet Another Unpacker for 1C:Enterprise to Sync Depot with Git for Code Review

���������� ������������� ��������� 1� � git

* ������� �������������� 1Script ������ => 1.0.9.100 [����������� �����������](https://bitbucket.org/EvilBeaver/1script/wiki/Home) 

## ������� �������������

* ���������� 1Script, ����� oscript.exe �������� �������� � %PATH%
* ���������� ����������� v8unpack.exe � ���������� � ������������� 1Script
* ��������� ������� ���������� (��� ������������ ���������� ��������� � ������ �������� ������)
* ��������� � ������ ���
  * ��������� ���� ������� � �������������� ���������� ����� � �������, � ����� ��������� e-mail ������
  * ������� ��������� ������ ��� ���������� (���������� ��� ����� ������� ������������ ERP 2.0 ����������� ����� 15 �����)
* ��������� �������� ������������� ��� ����������� ������� ���������� � ������������ **code climate**

## �������� ������-������

* �������� ���� ������ �������

> 

* ����� ����� ALM � ���� ��� ����������� ������ ��� ������������ �� CMMI (��� � ������ due diligense)

>

* Agile ��� ���������� �� 1�, �������� ��������������� �� ������� 1� � ������, ������, ������

## ��������� �������

��� ������ ���������� ��������� ������� ����������

```
cp profile.yml.example my-repo.yml
```

� ������� �������

```
storage_dir: \\depot-server\depot-erp-20\main\ # ����� � ���������� 1�
git_local_repo: d:\\git-for-erp\ # ��������� �����������, � ������� ����� ����������� ��������� �����������
v8_executable: C:\Program Files (x86)\1cv8\8.3.6.2041\bin\1cv8.exe # ������ ����� � ������������ ����� ��������� 1� ������ ������ 8.3.6.*
git_executable: C:\Program Files (x86)\Git\bin\git.exe # ������ ����� ��������� ������������ ����� git (MSGit ��� Windows)
git_remote_repo: file:///d:/repos/erp-20/ # ����������� ����� bare ����������� (�� ����������� �� ��������� ����������� ��� �������� ������������ ��������) 
git_email_domain: my-company.com # ����� ������� ������� ������ � ���������, ����� ����������� ��� ������� �������������� ��������� e-mail �������) 
unpack_dir: d:\git-for-erp\src\ # ������� ��� ���������� 
branch: master # ����� � ������� ����� ���������� ��������� (� ������ ������� ���������� �������� ����� ������������ ������������ ������������ ����� develop, hotfix � �.�.)
```

## ������� ������� �������

```
oscript.exe vanessa-unpack.os ./my-repo.yml
```

� ������ ������� ������� ����������� ������� ������������ ��������� �����������, ��� ��� �� ���� ����� ������, �� ����� ������ �� ������� ������ �� ���������� �������� �������.
������� � ���� ������ ���������� ��������� ������������ ������� 

> ������ bat ����� ��� �������������

```
@echo �������� ��������� ����������� �� �������
cd d:\\git-for-erp\ 
set GIT_AUTHOR_DATE="Mon, 1 Jan 2001 04:00:00 +0300"
set GIT_COMMITTER_DATE="Mon, 1 Jan 2001 04:00:00 +0300"
git add -A
git commit -a -m "Start integration with dirty date" --author="My Name <me@example.com>"
git push
@echo �������� �������������� ����������
mkdir d:\git-for-erp\src\ 
```

� ������ ����� ������������ 2 "���������� ���������" ������� ��������� ���������������� ����������� ������, ��� ����� ��������� ������ ��������� 1�


## ������� ������� �������

��� ������������� ��������� ���������� ��������� �������� �������

```
oscript.exe vanessa-unpack.os ./my-repo.yml
```

�� ����� ������� ������� ����������

* �������� ������� ��������� � ���� XML �����
* �������� ���� ������� � �� ������� �������������

����� ����� ��������� �� ���������� ���� ������ **unpack_dir** 

��� ������������ ������������� ����������

* ������� ��������� ������ � ����� VERSION � �������� **unpack_dir**

```
<?xml version="1.0" encoding="UTF-8"?>
<VERSION>������� ������ - 100 ������ �����</VERSION>

```


* ������� ������������ ������� � ����� AUTHORS � �������� **unpack_dir**

```
����=Ivan Kojedub <ikojedub@examle.com>
����=Maria Nesterenko <mnesterenko@example.com>
```

## ������������� ����������� ��������

* ��� ���������� Windows Server - taskshd.msc: ������� ������ ����� ����������� (������������� ����� ����������� �� 15 �� 30 �����)
* ��� ���������� CI �������� - �������� ������������ Jenkins � �������� �������������� �������� �� ��������� ����� 1CD (����� ���� ���������)
* ��� ���������� linux - cron: ������ ������ ������������� �������� �������� � ���������� �������������

> ������ � linux ��������� �������������� ����� wine (wine oscript.exe ...)

## ������ �������

```
oscript.exe vanessa-unpack.os ./my-repo.yml -debug
```
� ���� ������ ����� ��������� ���������� ���������, ��� ������������ ������� ��������� ���������

## ������� "��������������" � ������������

* � 2012 ���� ������ ���������� � ���� ��������� v83unpack https://github.com/pumbaEO/v83unpack
* � 2013 ���� ������ ����������� ����� ������������ 1� ��� ���������� ��������� �������� 1� https://github.com/xDrivenDevelopment/v83unpack 
* � 2014 ���� ������ ��� ��������� ���������� �� 1Script ������ https://bitbucket.org/EvilBeaver

## �����������

* ��������� ������ ����� ���������� **bsl**
* ������� ������ ������������ ��� ������� ���������� ��������� OpenProject/Redmine

 


