---


---

<h1 id="rclone">rclone</h1>
<h2 id="windows挂载">Windows挂载</h2>
<p>D:\A-Software\rclone-v1.64.2-windows-amd64\rclone.exe mount alist:/ K: --vfs-cache-mode full  --header “Referer:<a href="https://www.aliyundrive.com/">https://www.aliyundrive.com/</a>”<br>
使用<a href="https://nssm.cc/">nssm</a>注入服务，需要注意使用本地账号启动，不然启动不了</p>
<h2 id="rclone配置：">rclone配置：</h2>
<p>Editing existing “alist” remote with options:</p>
<ul>
<li>
<p>type: webdav</p>
</li>
<li>
<p>url: <a href="http://192.168.x.x:5244/dav">http://192.168.x.x:5244/dav</a></p>
</li>
<li>
<p>vendor: other</p>
</li>
<li>
<p>user: admin</p>
</li>
<li>
<p>pass: *** ENCRYPTED ***</p>
</li>
</ul>
<p><a href="https://github.com/rclone/rclone">https://github.com/rclone/rclone</a></p>
<p><a href="https://github.com/winfsp/winfsp">https://github.com/winfsp/winfsp</a></p>

