---
title: "Testen des Anbieters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbieter, Testen"
  - "Testen von Anbietern"
  - "Testen, OLE DB-Anbieter"
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Testen des Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vor der Freigabe eines Anbieters sollten die folgenden Tests in der angegebenen Reihenfolge durchgeführt werden.  Die Tests gewährleisten, dass der Anbieter von den meisten potenziellen Benutzern problemlos verwendet werden kann.  
  
1.  Testen Sie den Anbieter mit einer [Consumeranwendung](../../data/oledb/creating-an-ole-db-consumer.md), die unter Verwendung der OLE DB\-Consumervorlagen geschrieben wurde.  Der Testconsumer sollte alle Funktionsbereiche des Anbieters \(den gesamten hinzugefügten oder geänderten Code\) abdecken.  
  
2.  Testen Sie den Anbieter unter Verwendung einer mit ADO geschriebenen Consumeranwendung.  Die meisten Entwickler \(insbesondere Microsoft Visual Basic\- und Microsoft C\#\-Entwickler\) verwenden ADO oder ADO.NET für ihre Consumeranwendungen.  Der Testconsumer sollte alle Funktionsbereiche des Anbieters enthalten.  Ein Beispiel für eine ADO\-Consumeranwendung finden Sie unter [ADO Code Examples in Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx) \(nur auf Englisch verfügbar\).  
  
3.  Führen Sie die OLE DB\-Konformitätstests \(einschließlich der ADO\-Konformitätstests\) durch, um sicherzustellen, dass der Anbieter dem Level 0\-Standard für OLE DB\-Anbieter entspricht. \(Eine Erläuterung der Ebene 0, testet Suche nach Übereinstimmung "OLE DB Ebenen\-0" an [OLE DB Programmierhandbuch](http://go.microsoft.com/fwlink/?LinkId=121548).  Diese Tests und die zugehörige Dokumentation sind im Microsoft Data Access\-SDK von Visual C\+\+ enthalten.  Darüber hinaus können Sie mithilfe der Tests sicherstellen, dass der Anbieter einwandfrei funktioniert, wenn er von anderen [Dienstanbietern](../../data/oledb/ole-db-resource-pooling-and-services.md) aggregiert wird. Diese Tests sind auch hilfreich, wenn Sie Eigenschaften ändern oder hinzufügen.  Weitere Informationen zu den Konformitätstests finden Sie in der Infodatei zum Microsoft Data Access\-SDK auf einer der Visual Studio\-CDs.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)