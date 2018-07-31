---
title: Empfangen von Benachrichtigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fdef616456b98086bf9490297d68c98596b2dca4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338969"
---
# <a name="receiving-notifications"></a>Empfangen von Benachrichtigungen
OLE DB stellt Schnittstellen bereit, für den Empfang von Benachrichtigungen, wenn Ereignisse auftreten. Diese werden beschrieben [OLE DB-Objekt Benachrichtigungen](https://msdn.microsoft.com/library/ms725406.aspx) in die *OLE DB-Programmierreferenz*. Setup dieser Ereignisse wird den COM-Verbindungspunkt Standardmechanismus verwendet. Z. B. ein ATL-Objekt, das Ereignisse über abrufen möchte `IRowsetNotify` implementiert die `IRowsetNotify` -Schnittstelle durch Hinzufügen von `IRowsetNotify` auf die abgeleitete Klasse-Liste, und es über ein COM_INTERFACE_ENTRY-Makro verfügbar zu machen.  
  
 `IRowsetNotify` verfügt über drei Methoden, die zu verschiedenen Zeiten aufgerufen werden können. Wenn Sie nur eine dieser Methoden reagieren möchten, können Sie mithilfe der [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) -Klasse, die für die Methoden gibt E_NOTIMPL zurück Sie nicht interessiert sind.  
  
 Bei der Erstellung des Rowsets müssen Sie dem Anbieter anweisen, wirklich das zurückgegebene Rowset-Objekt, unterstützt `IConnectionPointContainer`, das ist erforderlich, um die Benachrichtigung eingerichtet.  
  
 Der folgende Code zeigt, öffnen Sie das Rowset von einem ATL-Objekt, und Verwenden der `AtlAdvise` Funktion, um den Benachrichtigungsempfänger einzurichten. `AtlAdvise` Gibt ein Cookie, das verwendet wird, wenn Sie aufrufen `AtlUnadvise`.  
  
```cpp  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  
product.Open(session, _T("Products"), &propset);  
  
AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)