<html lang="en"><head>
    <meta charset="UTF-8">
    <title></title>
<style id="system" type="text/css">h1,h2,h3,h4,h5,h6,p,blockquote {    margin: 0;    padding: 0;}body {    font-family: "Helvetica Neue", Helvetica, "Hiragino Sans GB", Arial, sans-serif;    font-size: 13px;    line-height: 18px;    color: #737373;    margin: 10px 13px 10px 13px;}a {    color: #0069d6;}a:hover {    color: #0050a3;    text-decoration: none;}a img {    border: none;}p {    margin-bottom: 9px;}h1,h2,h3,h4,h5,h6 {    color: #404040;    line-height: 36px;}h1 {    margin-bottom: 18px;    font-size: 30px;}h2 {    font-size: 24px;}h3 {    font-size: 18px;}h4 {    font-size: 16px;}h5 {    font-size: 14px;}h6 {    font-size: 13px;}hr {    margin: 0 0 19px;    border: 0;    border-bottom: 1px solid #ccc;}blockquote {    padding: 13px 13px 21px 15px;    margin-bottom: 18px;    font-family:georgia,serif;    font-style: italic;}blockquote:before {    content:"C";    font-size:40px;    margin-left:-10px;    font-family:georgia,serif;    color:#eee;}blockquote p {    font-size: 14px;    font-weight: 300;    line-height: 18px;    margin-bottom: 0;    font-style: italic;}code, pre {    font-family: Monaco, Andale Mono, Courier New, monospace;}code {    background-color: #fee9cc;    color: rgba(0, 0, 0, 0.75);    padding: 1px 3px;    font-size: 12px;    -webkit-border-radius: 3px;    -moz-border-radius: 3px;    border-radius: 3px;}pre {    display: block;    padding: 14px;    margin: 0 0 18px;    line-height: 16px;    font-size: 11px;    border: 1px solid #d9d9d9;    white-space: pre-wrap;    word-wrap: break-word;}pre code {    background-color: #fff;    color:#737373;    font-size: 11px;    padding: 0;}@media screen and (min-width: 768px) {    body {        width: 748px;        margin:10px auto;    }}</style><style id="custom" type="text/css"></style></head>
<body><p>由于比赛是CTF和linux 实战渗透的结合，比赛的前后整理了关于主机常见端口漏洞。

</p>
<h2>21端口</h2>
<p>FTP(file Transfer Protocol)文件传输协议<br>1.匿名访问——未授权访问<br>2.弱密码<br>3.配置不当 直接 cd / &amp;&amp; dir<br>4.FTP使用明文传输技术-嗅探

</p>
<h2>22端口</h2>
<p>SSH SSH服务基本会出现在我们的linux服务器、网络设备上，而且SSH服务开启后的设置很多都是默认的<br>1.弱口令<br>2.防火墙SSH后门<br>3.28退格 OpenSSL

</p>
<h2>23端口</h2>
<p>TLENET<br>弱口令

</p>
<h2>53端口</h2>
<p>DNS域传送信息泄露  dig axfr @xx.xx.xx.xx xx.xx.xx.xx<br>DNS劫持<br>DNS缓存投毒<br>DNS欺骗<br>DNS隧道技术刺穿防火墙

</p>
<h2>81端口</h2>
<p>ipcam的web端口<br>弱口令123端口<br>NTP（Network Time Protocol）它是用来同步网络中各个计算机的时间的协议。<br>1.可以基于NTP的反射和放大攻击<br>2.NTP反射型doos攻击

</p>
<h2>389端口</h2>
<p>LDAP协议 轻量级目录访问协议<br>1.注入<br>2.未授权访问<br>3.弱密码

</p>
<h2>443端口</h2>
<p>heartbleed心脏出血

</p>
<h2>873端口</h2>
<p>RSYNC 远程同步功能<br>1.匿名访问<br>2.弱口令<br>rsync xxx.xxx.xxx.xxx::

</p>
<h2>1352端口</h2>
<p>Louts<br>1.弱口令<br>2.文件泄露<br><a href="http://**.**.**.**/names.nsf/">http://**.**.**.**/names.nsf/</a>

</p>
<h2>1433端口</h2>
<p>mssql<br>弱口令

</p>
<h2>1521端口</h2>
<p>ocral<br>1.弱口令<br>2.溢出

</p>
<h2>2375端口</h2>
<p>docker remote api<br>接口未授权访问<br>访问 <a href="http://xxx.xxx.xxx.xxx:2375/containers/json">http://xxx.xxx.xxx.xxx:2375/containers/json</a> 会返回服务器的container列表<br>docker -H tcp://xxx.xxx.xxx.xxx:2375 images<br>docker -H tcp://xxx.xxx.xxx.xxx:2375 run -it --entrypoint /bin/bash ubuntu "-h"

</p>
<h2>3306端口</h2>
<p>mysql<br>弱口令  

</p>
<h2>5000端口</h2>
<p>SysBase<br>1.弱口令<br>2.命令注入

</p>
<h2>5432端口</h2>
<p>PostgreSQL<br>弱口令

</p>
<h2>6379端口</h2>
<p>redis<br>未授权访问利用redis写getshall<br>redis-cli -h xxx.xxx.xxx.xxx -p 6379

</p>
<h2>7001端口</h2>
<p>weblogic<br>弱口令   <a href="http://xxx.xxx.xxx.xxx:7001/console/login/LoginForm.jsp">http://xxx.xxx.xxx.xxx:7001/console/login/LoginForm.jsp</a><br>weblogic/weblogic<br>可探测内网

</p>
<h2>8080端口</h2>
<p>java web中间组件<br>tomcat 弱口令 <a href="http://xxx.xxx.xxx.xxx:8080/manager/html">http://xxx.xxx.xxx.xxx:8080/manager/html</a> 部署war包<br>GlassFish<br>1.弱口令<br>2.任意文件读取<br>3.认证绕过<br>Resin<br>1.目录遍历<br>2.远程文件读取<br><a href="http://xxx.xxx.xxx.xxx/%20../web-inf/">http://xxx.xxx.xxx.xxx/%20../web-inf/</a><br><a href="http://xxx.xxx.xxx.xxx:8088/resin-doc/resource/tutorial/jndi-appconfig/test?inputFile=/etc/passwd">http://xxx.xxx.xxx.xxx:8088/resin-doc/resource/tutorial/jndi-appconfig/test?inputFile=/etc/passwd</a>

</p>
<h2>8089端口</h2>
<p>jboss 弱口令admin/admin 部署war包 getshell<br><a href="http://**.**.**.**/jmx-console/">http://**.**.**.**/jmx-console/</a><br><a href="http://**.**.**.**/admin-console/">http://**.**.**.**/admin-console/</a>  

</p>
<h2>8649端口</h2>
<p>ganglia未授权访问<br>通过http协议获取相关监控的xml信息<br>nmap扫描脚本  nmap --script ganglia-info --script-args ganglia-info.timeout=60,ganglia-info.bytes=100000 -p <port> <tager>

</tager></port></p>
<h2>9080 9081 9090端口</h2>
<p>Websphere<br>1.弱口令（console）<br>2.任意文件泄露<br>3.java反序列化<br>可导致XML配置文件泄露<a href="http://xxx.xxx.xxx.xxx/ffp/à?/WEB-INF/modules/struts-config-codingShare.xml">http://xxx.xxx.xxx.xxx/ffp/à?/WEB-INF/modules/struts-config-codingShare.xml</a><br>弱口令<a href="http://xxx.xxx.xxx.xxx:9080/ibm/console/secure/logon.do">http://xxx.xxx.xxx.xxx:9080/ibm/console/secure/logon.do</a> 

</p>
<h2>27017端口</h2>
<p>MongoDBB<br>弱口令<br>未授权访问
Edit By <a href="http://mahua.jser.me">MaHua</a></p>
</body></html>
