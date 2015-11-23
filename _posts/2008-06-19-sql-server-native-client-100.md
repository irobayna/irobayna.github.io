---
title: SQL Server Native Client 10.0
author: admin
layout: post
permalink: /2008/06/19/sql-server-native-client-100/
shorturl:
  - http://bit.ly/i7KXTW
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/herCAq
categories:
  - ADO.NET
  - Delphi
  - Microsoft Sql Server 2008
  - technology
tags:
  - ADO
  - ADO.NET
  - Delphi
  - OLE DB Provider
  - PrompDataSource
  - SQL Server
---
<span style="color: #ff0000;">The new SQL Server Native Client 10.0 app appears not to return the password back when using Delphi&#8217;s ADO PromptDataSource</span>

<span style="color: #0000ff;">Update: 6/20/2008<br /> There is definitely a bug in the Dialog not in the PrompDataSource.  The solution is posted at the end of the article.</span>

Microsoft SQL Server 2008 installs a new OLE DB Provider called: &#8220;**SQL Server Native Client 10.0**&#8221; Here is the Data Link Properties image:

[![datalinkproperties_b.JPG][1]][2]

Bringing up the ADO Connection Dialog:

`CS  := PromptDataSource( Handle, "");`

One change I can see is that using Delphi&#8217;s **PrompDataSource **function, it returns a different string than previous providers.  **The Password field seems to be missing:**

`'Provider=SQLNCLI10.1;Integrated Security="";Persist Security Info=False;User ID=sa;Initial Catalog=XIMS;Data Source=(local);Initial File Name="";Server SPN=""'<br />
`  
Here is the output from **PrompDataSource **using Microsoft OLE DB  Provider for SQL Server:

`'Provider=SQLOLEDB.1;<span style="color: #ff0000;">Password=1234</span>;Persist Security Info=True;User ID=sa;Initial Catalog=Rome;Data Source=(local)'`

Here is an image of the old Data Link Properties editor:

[![datalinkproperties_d.JPG][3]][4]

## The new Dialog has three key differences :

  1. You can used mix mode authentication (nothing new here) but also use Windows NT Integrated Security and specify a Server SPN(service principal name).  This is quite flexible.  For more info [click ][5]here
  2. Be able to attache a database file as a database Name &#8211; I am guessing this is here due to all the enhancements SQL Server 2008 offers in regards to backing up, restore, compression and encryption database files.
  3. Be able to Change the database password directly from this page.

<span style="text-decoration: line-through;">If you find out how to retrieve the &#8220;whole&#8221; string let me know. </span>

Solution: go into the ALL tab and make sure you set **Persist Security Info** to TRUE the default (today) is FALSE (thanks Ken!)

[![datalinkproperties_e.JPG][6]][7]

You might be interested in finding out [what&#8217;s new in SQL Server 2008][8]

 [1]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_b.JPG
 [2]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_b.JPG "datalinkproperties_b.JPG"
 [3]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_d.JPG
 [4]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_d.JPG "datalinkproperties_d.JPG"
 [5]: http://support.microsoft.com/kb/909801
 [6]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_e.JPG
 [7]: http://blogs.bikecrawler.com/wp-content/uploads/2008/06/datalinkproperties_e.JPG "datalinkproperties_e.JPG"
 [8]: http://blogs.bikecrawler.com/2008/06/08/microsoft-teched-2008-orlando-florida-update/