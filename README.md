# Wyl-K Web Vulnerability Scanner

WebMap 是一个功能强大的Web漏洞扫描器，能够检测SQL注入、XSS、文件上传等常见Web安全漏洞。

## 功能特点

- 检测SQL注入漏洞
- 检测跨站脚本(XSS)漏洞
- 检测文件上传漏洞
- 检测目录遍历漏洞
- 检测弱密码和暴力破解登录
- 网站爬虫和链接提取
- 生成不同类型的WebShell
- 支持多线程扫描
- 生成详细的扫描报告

## 安装说明

### 环境要求
- Python 3.7+ 
- 所需依赖包

### 安装步骤
1. 克隆或下载项目代码到本地
2. 安装依赖包:
   ```
   pip install requests beautifulsoup4 colorama
   ```
   或者创建requirements.txt文件并添加以下内容:
   ```
   requests
   beautifulsoup4
   colorama
   ```
   然后运行:
   ```
   pip install -r requirements.txt
   ```
3. 运行扫描器:
   ```
   python web_vulnerability_scanner.py -u http://example.com
   ```
4. 或者使用已打包的可执行文件:
   ```
   dist\webmap.exe -u http://example.com
   ```

## 使用方法

### 基本扫描
```
# 使用Python脚本
python web_vulnerability_scanner.py -u http://example.com

# 使用可执行文件
dist\webmap.exe -u http://example.com
```

### 高级扫描选项
```
# 设置扫描深度为5
python web_vulnerability_scanner.py -u http://example.com -d 5
dist\webmap.exe -u http://example.com -d 5

# 启用多线程扫描(10线程)
python web_vulnerability_scanner.py -u http://example.com -t 10
dist\webmap.exe -u http://example.com -t 10

# 保存报告到指定文件
python web_vulnerability_scanner.py -u http://example.com -o report.json
dist\webmap.exe -u http://example.com -o report.json

# 启用详细输出
python web_vulnerability_scanner.py -u http://example.com -v
dist\webmap.exe -u http://example.com -v

# 启用暴力破解登录
python web_vulnerability_scanner.py -u http://example.com -b
dist\webmap.exe -u http://example.com -b
```

### WebShell生成功能
```
# 生成简单PHP WebShell
python web_vulnerability_scanner.py --generate-webshell --webshell-type php --webshell-template simple
dist\webmap.exe --generate-webshell --webshell-type php --webshell-template simple

# 生成反向Shell
python web_vulnerability_scanner.py --generate-webshell --webshell-type php --webshell-template reverse_shell --reverse-ip 192.168.1.100 --reverse-port 4444
dist\webmap.exe --generate-webshell --webshell-type php --webshell-template reverse_shell --reverse-ip 192.168.1.100 --reverse-port 4444

# 自动生成WebShell并保存到文件
python web_vulnerability_scanner.py --auto-webshell php --output-webshell shell.php
```

## 命令行参数

- `-u`, `--url`: 目标URL (必需)
- `-t`, `--threads`: 线程数 (默认: 5)
- `-o`, `--output`: 报告输出文件 (默认: scan_report_<timestamp>.json)
- `-d`, `--depth`: 爬取深度 (默认: 3)
- `-T`, `--timeout`: 请求超时时间 (默认: 10秒)
- `-a`, `--user-agent`: 自定义用户代理
- `-v`, `--verbose`: 启用详细输出
- `-b`, `--brute-force`: 启用暴力破解登录
- `-U`, `--usernames`: 用户名字典文件路径
- `-P`, `--passwords`: 密码字典文件路径
- `-m`, `--max-attempts`: 最大登录尝试次数 (默认: 100)
- `--generate-webshell`: 生成WebShell
- `--webshell-type`: WebShell类型 (php, asp, jsp, 默认: php)
- `--webshell-template`: WebShell模板 (simple, post, base64, obfuscated, reverse_shell, 默认: simple)
- `--reverse-ip`: 反向Shell的IP地址
- `--reverse-port`: 反向Shell的端口 (默认: 4444)
- `--output-webshell`: WebShell输出文件
- `--auto-webshell`: 自动生成WebShell (指定文件扩展名)

## 注意事项
1. 请仅在有授权的网站上使用本工具
2. 未经许可对他人网站进行扫描可能违反法律法规
3. 对于大型网站，建议调整扫描深度和线程数以避免对目标服务器造成过大压力
4. WebShell生成功能仅用于合法的渗透测试和安全评估

## 版本信息
当前版本: 1.0.1

## 免责声明
本工具仅供学习和研究使用，作者不对使用本工具造成的任何损失或违法行为负责。