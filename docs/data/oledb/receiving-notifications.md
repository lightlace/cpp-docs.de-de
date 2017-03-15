---
title: "Empfangen von Benachrichtigungen | Microsoft Docs"
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
  - "Ereignisse [C++], Benachrichtigungen in OLE DB"
  - "Benachrichtigungen [C++], Ereignisse"
  - "Benachrichtigungen [C++], OLE DB-Consumer"
  - "OLE DB-Consumer, Benachrichtigungen"
  - "OLE DB-Anbieter, Benachrichtigungen"
  - "Empfangen von Benachrichtigungen in OLE DB"
  - "Rowsets, Ereignisbenachrichtigungen"
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Empfangen von Benachrichtigungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB bietet Schnittstellen zum Empfang von Benachrichtigungen, wenn Ereignisse auftreten.  Eine Beschreibung finden Sie unter [OLE DB\-Objektbenachrichtigungen](https://msdn.microsoft.com/en-us/library/ms725406.aspx) in der *OLE\-Programmierreferenz*.  Das Setup dieser Ereignisse verwendet den standardmäßigen COM\-Verbindungspunktmechanismus.  Ein ATL\-Objekt, das Ereignisse über `IRowsetNotify` abrufen möchte, implementiert beispielsweise die `IRowsetNotify`\-Schnittstelle, indem `IRowsetNotify` zu der aus Klassen abgeleiteten Liste hinzugefügt und mit einem **COM\_INTERFACE\_ENTRY**\-Makro offen gelegt wird.  
  
 `IRowsetNotify` besitzt drei Methoden, die zu verschiedenen Zeiten aufgerufen werden können.  Wenn Sie nur auf eine dieser Methoden reagieren möchten, können Sie die [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)\-Klasse verwenden, die **E\_NOTIMPL** für die Methoden zurückgibt, an denen Sie nicht interessiert sind.  
  
 Wenn Sie das Rowset erstellen, müssen Sie dem Anbieter mitteilen, dass das zurückgegebene Rowset\-Objekt **IConnectionPointContainer** unterstützen soll. Dies ist notwendig, um die Benachrichtigung einzurichten.  
  
 Im folgenden Code wird dargestellt, wie Sie ein Rowset über ein ATL\-Objekt öffnen und anschließend die `AtlAdvise`\-Funktion verwenden, um die Benachrichtigungssenke einzurichten.  `AtlAdvise` gibt ein Cookie zurück, das beim Aufruf von `AtlUnadvise` verwendet wird.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)