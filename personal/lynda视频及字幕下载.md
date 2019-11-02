# lynda视频及字幕批量下载
*方雪至 2019-10-14*
## Pre-request
- 一个可用的梯子（国内下载速度慢）
- 一个可用的lynda账号或其他人分享的cookies
- chrome插件
    - xpath helper
    - cookies.txt
## Procedure
- 登录lynda会员账号
- chrome中的xpath helper插件找到列表中每个视频的地址
    > //li//ul//li//div//a/@href
- chrome中的cookies.txt插件下载当前课程页的cookies信息，并将保存的cookies.txt放到youtube-dl安装目录下
- youtube-dl 利用cookies 解析下载视频和字幕
    > youtube-dl --cookies cookies.txt --all-subs xxx.html
- youtube-dl 按目录顺序保存文件名并写入txt文件，方便查找
    - 两种方式
        > - youtube-dl --cookies cookies.txt --get-filename xxx.html >> list.txt
        > - youtube-dl --cookies cookies.txt --get-filename xxx.html | tee -a list.txt
- 写入bash文件，批量运行
    > bash *.sh
