---
title: Save is not permitted in SQL Server 2008
author: admin
layout: post
permalink: /2009/05/16/save-is-not-permitted-in-sql-server-2008/
shorturl:
  - http://bit.ly/gR4EY8
short-url:
  - http://bit.ly/fw8F7f
categories:
  - Microsoft Sql Server 2008
  - technology
---
<div id="msgcns!98EC8584C8BBED54!849" class="bvMsg">
  <div>
    In <a href="http://go.microsoft.com/fwlink/?LinkID=103186" target="_blank">SQL Server 2008</a>, you might have gotten this message when trying to change the columns in some tables, add columns or change nullity conditions. <strong>&#8220;Save is not permitted&#8221;</strong> tables have to be dropped and re-created.  The only choice you have is to click cancel, or to choose to save the message to a text file, which is, i think, not very useful .
  </div>
  
  <div>
    Here is the solution:
  </div>
  
  <div>
    Tools -> Options -> Designers, and unchecked the option &#8220;Prevent saving changes that require table re-creation&#8221;.
  </div>
</div>