---
title: How to convert a SqlDataReader dataset to JSON
author: admin
layout: post
permalink: /2010/12/04/how-to-convert-a-sqldatareader-dataset-to-json/
shorturl:
  - http://bit.ly/fZ1YUM
amazon-product-excerpt-hook-override:
  - 3
amazon-product-content-hook-override:
  - 2
amazon-product-newwindow:
  - 3
short-url:
  - http://bit.ly/ftH9nF
categories:
  - 'C#'
  - science
  - Visual Studio 2010
---
<pre class="brush:csharp">void WriteDataReader(StringBuilder sb, IDataReader reader)
        {
            if (reader == null || reader.FieldCount == 0)
            {
                sb.Append("null");
                return;
            }

            int rowCount = 0;

            sb.Append(@"{""Row"":[");

            while (reader.Read())
            {
                sb.Append("{");

                for (int i = 0; i &lt; reader.FieldCount; i++)
                {
                    sb.Append("\"" + reader.GetName(i) + "\":");
                    sb.Append("\"" + reader[i] + "\"");

                    sb.Append(i == reader.FieldCount - 1 ? "" : ",");

                }

                sb.Append("},");

                rowCount++;
            }

            if (rowCount &gt; 0)
            {
                int index = sb.ToString().LastIndexOf(",");
                sb.Remove(index, 1);
            }

            sb.Append("]}");
        }</pre>