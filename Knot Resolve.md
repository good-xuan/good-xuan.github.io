---


---

<h1 id="knot-resolve">Knot Resolve</h1>
<h2 id="修改-etcfstab">修改 /etc/fstab</h2>
<p>tmpfs  /var/cache/knot-resolver  tmpfs  rw,size=2G,uid=knot-resolver,gid=knot-resolver,nosuid,nodev,noexec,mode=0700 0 0<br>
<strong>简写</strong><br>
tmpfs  /var/cache/knot-resolver  tmpfs  rw,size=110M 0 0</p>
<h2 id="knot-reesolve-配置">Knot Reesolve 配置</h2>
<h3 id="vi-etcknot-resolverkresd.conf">vi /etc/knot-resolver/kresd.conf</h3>
<p><em>监听地址</em><br>
net.listen({‘127.0.0.1’,‘10.10.X.X’}, 53, { kind = ‘dns’ })<br>
<em>关闭dnssec</em><br>
trust_anchors.remove(’.’)<br>
<em>转发</em><br>
policy.add(policy.all(policy.FORWARD({‘223.5.5.5’, ‘119.29.29.29’})))<br>
<em>转发指定域名到指定dns服务器</em><br>
policy.add(policy.suffix(policy.FORWARD(‘119.29.29.29’),{todname(‘<a href="http://example.com">example.com</a>.’)}))<br>
<em>缓存大小</em><br>
cache.size = 100 * MB<br>
<em>自定义记录</em><br>
hints[‘<a href="http://kb.wscnbj.cn">kb.wscnbj.cn</a>’] = ‘10.10.x.x’<br>
hints[‘<a href="http://excel.wscnbj.cn">excel.wscnbj.cn</a>’] = ‘10.10.x.x’</p>

