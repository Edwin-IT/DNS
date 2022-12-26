<p align="center">
<img src="https://imgur.com/kup8h6K.png" height="25%" width="25%" alt="DNS"/>
</p>

<h1>DNS</h1>
This tutorial helps build intuition for DNS by configuring A-Records and CNAME Record in DNS manager in a Domain Controller and seeing the effects in a Client Virtual Machine.<br />


<h2>Environments and Technologies Used</h2>

- Command line
- DNS Manager

<h2>Overview</h2>

- Step 1:	A-Record 
- Step 2: Local DNS Cache
- Step 3: CNAME Record


<h2>Steps</h2>

<p>
<img src="https://imgur.com/IFC8bvS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/3MQusv2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/IFC8bvS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 1: Log into DC-1 and Client-1 as domain admin account. In Client-1 ping “mainframe”,it will fail. Go to DC-1 and create a DNS A-record for “mainframe” using DC-1’s Private IP address by going to DNS Manager, DC-1, mydomain.com. Now, ping again in Client-1; this time it will work.
</p>
<br />

<p>
<img src="https://imgur.com/Fekv3vM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/wWTdKmV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/lH7FRpl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 2: In DC-1 change mainframe’s IP address to 8.8.8.8. Go to Client-1 and ping “mainframe”. It will still pings the old address.  Flush the DNS cache with ipconfig /flushdns.  Ping “mainframe” again. Now, the new ip address will show up.
</p>
<br />

<p>
<img src="https://imgur.com/kjwNuFq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/9tOfa7y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Step 3: In DC-1 create a CNAME record that points “search” to www.google.com. Ping “search” in Client-1 and www.google.com will be the result.
</p>
<br />
