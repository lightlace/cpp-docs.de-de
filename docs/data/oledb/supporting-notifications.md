---
title: "Unterstützen von Benachrichtigungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- events [C++], notifications in OLE DB
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB provider templates, notifications
- OLE DB providers, notifications
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbdb3b7faaec99f9893df29e8d368fd05c8fd111
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="supporting-notifications"></a>Unterstützen von Benachrichtigungen
## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Implementieren von Verbindungspunkt-Schnittstellen für Anbieter und Consumer  
 Um Benachrichtigungen zu implementieren, muss von eine Klasse erben [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) und [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` die Anbieter-Website für die Verbindungspunkt-Schnittstelle implementiert [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx). `IRowsetNotifyCP` implementiert broadcast Funktionen, um die advise-Listener auf dem Verbindungspunkt **IID_IRowsetNotify** Änderungen an den Inhalt des Rowsets.  
  
 Beachten Sie, die Sie implementieren und registrieren Außerdem müssen `IRowsetNotify` auf Consumer (auch bekannt als die Senke) mit [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , damit der Consumer Benachrichtigungen behandeln kann. Informationen zum Implementieren der Verbindungspunkt-Schnittstelle auf der Consumer finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md).  
  
 Darüber hinaus muss die Klasse auch eine Zuordnung enthalten, die den Verbindung Point-Eintrag ist wie folgt definiert:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>Hinzufügen von IRowsetNotify  
 Hinzuzufügende `IRowsetNotify`, müssen Sie die hinzuzufügenden `IConnectionPointContainerImpl<rowset-name>` und `IRowsetNotifyCP<rowset-name>` der Vererbungskette.  
  
 Hier ist z. B. die Vererbungskette für `RUpdateRowset` in [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Der Beispielcode weicht möglicherweise von den hier genannten der; den Code sollte als aktuellere Version angesehen werden.  
  
```cpp
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan>>, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll >>,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### <a name="setting-com-map-entries"></a>COM-Zuordnungseinträge festlegen  
 Sie müssen auch die COM-Zuordnung im Rowset Folgendes hinzu:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Diese Makros jedermann Aufrufen `QueryInterface` für Container für Ihre Verbindung (die Grundlage für `IRowsetNotify`) die angeforderte Schnittstelle für den Anbieter gefunden. Ein Beispiel zum Verwenden von Verbindungspunkten finden Sie unter der ATL-POLYGON-Beispiel und -Lernprogramm.  
  
### <a name="setting-connection-point-map-entries"></a>Connection Point-Zuordnungseinträge festlegen  
 Sie müssen auch eine Verbindung Punkt Karte hinzufügen. Es sollte etwa folgendermaßen aussehen:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Diese Verbindung Punkt Zuordnung kann eine Komponente, die Suche nach der `IRowsetNotify` Schnittstelle in Ihrem Anbieter gefunden.  
  
### <a name="setting-properties"></a>Festlegen von Eigenschaften  
 Außerdem müssen Sie die folgenden Eigenschaften an Ihren Anbieter hinzufügen. Sie müssen nur zum Hinzufügen von Eigenschaften basierend auf den Schnittstellen, die Sie unterstützen.  
  
|Eigenschaft|Bei Unterstützung hinzufügen|  
|--------------|------------------------|  
|**DBPROP_IConnectionPointContainer**|Immer|  
|**DBPROP_NOTIFICATIONGRANULARITY**|Immer|  
|**DBPROP_NOTIFICATIONPHASES**|Immer|  
|**DBPROP_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE**|Immer|  
|DBPROP_NOTIFYROWFIRSTCHANGE|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWSETRELEASE**|Immer|  
|DBPROP_NOTIFYROWUNDOCHANGE|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 Ein Großteil der Implementierung für die Benachrichtigungen ist bereits in der OLE DB-Anbietervorlagen eingebettet sind. Wenn Sie keinen `IRowsetNotifyCP` der Vererbungskette entfernt der Compiler den gesamten Code aus Ihrem Kompilierungsstream, wodurch die Codegröße kleiner.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)