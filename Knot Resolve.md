---


---

<h1 id="knot-resolve">Knot Resolve</h1>
<h2 id="修改-etcfstab">修改 /etc/fstab</h2>
<p>tmpfs  /var/cache/knot-resolver  tmpfs  rw,size=2G,uid=knot-resolver,gid=knot-resolver,nosuid,nodev,noexec,mode=0700 0 0</p>
<h3 id="简写">简写</h3>
<p>tmpfs  /var/cache/knot-resolver  tmpfs  rw,size=110M 0 0</p>
<h2 id="knot-reesolve-配置">Knot Reesolve 配置</h2>
<h3 id="vi-etcknot-resolverkresd.conf">vi /etc/knot-resolver/kresd.conf</h3>
<p>net.listen({‘127.0.0.1’,‘10.10.X.X’}, 53, { kind = ‘dns’ })</p>
<p>trust_anchors.remove(’.’)</p>
<p>policy.add(policy.all(policy.FORWARD({‘223.5.5.5’, ‘119.29.29.29’})))</p>
<p>cache.size = 100 * MB</p>
<p>hints[‘<a href="http://kb.wscnbj.cn">kb.wscnbj.cn</a>’] = ‘10.10.x.x’</p>
<p>hints[‘<a href="http://excel.wscnbj.cn">excel.wscnbj.cn</a>’] = ‘10.10.x.x’</p>
<p>policy.add(policy.suffix(policy.FORWARD(‘119.29.29.29’),{todname(‘<a href="http://example.com">example.com</a>.’)}))</p>

