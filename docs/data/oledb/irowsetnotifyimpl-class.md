---
title: "IRowsetNotifyImpl-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetNotifyImpl"
  - "ATL::IRowsetNotifyImpl"
  - "IRowsetNotifyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyImpl-Klasse"
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetNotifyImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert und registriert [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) für den Consumer \(auch als Senke ""\) damit es Benachrichtigungen bearbeiten kann.  
  
## Syntax  
  
```  
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|Benachrichtigt den Consumer über alle Änderungen am Wert einer Spalte.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|Benachrichtigt den Consumer über die erste Änderung an einer Zeile oder über jede Änderung, die Auswirkungen auf die ganze Zeile hat.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|Benachrichtigt den Consumer über alle Änderungen, die Auswirkungen auf das gesamte Rowset haben.|  
  
## Hinweise  
 Siehe [Empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) über das Implementieren des Verbindungspunkts, für den Consumer herzustellen.  
  
 `IRowsetNotifyImpl` stellt eine blinde Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify`\-Methoden [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) und [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx).  Wenn Sie dieser Klasse erben, wenn Sie eine `IRowsetNotify`\-Schnittstelle implementieren, können Sie nur die Methoden implementieren, die Sie benötigen.  Sie müssen auch leere Implementierungen für die anderen Methoden bereitstellen.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP\-Klasse](../../data/oledb/irowsetnotifycp-class.md)