---
title: Empfangen von Benachrichtigungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50911440acbc7514b091a439d42bf73ee60353f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="receiving-notifications"></a>Empfangen von Benachrichtigungen
OLE DB stellt Schnittstellen bereit, für den Empfang von Benachrichtigungen, wenn Ereignisse auftreten. Diese Angaben werden in [OLE DB-Objekt Benachrichtigungen](https://msdn.microsoft.com/en-us/library/ms725406.aspx) in der *OLE DB Programmer's Reference*. Setup dieser Ereignisse verwendet, die COM-Verbindungspunkte Standardmechanismus. Z. B. ein ATL-Objekt, das Ereignisse über abrufen möchte `IRowsetNotify` implementiert die `IRowsetNotify` -Schnittstelle durch Hinzufügen von `IRowsetNotify` auf der Liste abgeleitete Klasse und das Verfügbarmachen von über eine **COM_INTERFACE_ENTRY** Makro.  
  
 `IRowsetNotify` verfügt über drei Methoden, die zu verschiedenen Zeiten aufgerufen werden kann. Wenn Sie nur eine dieser Methoden reagieren möchten, können Sie mithilfe der [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) zurück, welche **E_NOTIMPL** für die Methoden, die Sie nicht interessiert sind.  
  
 Bei der Erstellung des Rowsets müssen Aufschluss darüber, dem Anbieter, soll jedoch stattdessen das zurückgegebene Rowset unterstützen **IConnectionPointContainer**, das erforderlich ist, um die Benachrichtigung eingerichtet.  
  
 Der folgende Code zeigt, wie das Rowset von einem ATL-Objekt öffnen und Verwenden der `AtlAdvise` Funktion, um den Benachrichtigungsempfänger einzurichten. `AtlAdvise` Gibt ein Cookie, das verwendet wird, wenn Sie aufrufen `AtlUnadvise`.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  

product.Open(session, _T("Products"), &propset);  
  

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)