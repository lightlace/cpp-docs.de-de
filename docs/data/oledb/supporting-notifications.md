---
title: Unterstützen von Benachrichtigungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9fea13ef4a89ee2a1105702db4fe692c12643d2
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337939"
---
# <a name="supporting-notifications"></a>Unterstützen von Benachrichtigungen

## <a name="implementing-connection-point-interfaces-on-the-provider-and-consumer"></a>Implementieren von Verbindungsschnittstellen für Anbieter und Consumer  
 Um Benachrichtigungen zu implementieren, muss von eine Klasse erben [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) und [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md).  
  
 `IRowsetNotifyCP` die Website für die Verbindungspunkt-Schnittstelle implementiert [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx). `IRowsetNotifyCP` broadcast-implementiert Funktionen, um den Listener auf dem Verbindungspunkt empfehlen `IID_IRowsetNotify` von Änderungen an den Inhalt des Rowsets.  
  
 Beachten Sie, dass Sie auch implementieren registrieren müssen `IRowsetNotify` vom Consumer (auch bekannt als die Senke) mit [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , damit der Consumer mit Benachrichtigungen behandeln kann. Informationen zur Implementierung der vom Consumer der Verbindungspunkt-Schnittstelle finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md).  
  
 Darüber hinaus muss die Klasse auch eine Zuordnung enthalten, die der Verbindung des Punkt-Eintrag wie folgt definiert:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## <a name="adding-irowsetnotify"></a>IRowsetNotify hinzugefügt  
 Hinzuzufügende `IRowsetNotify`, müssen Sie die hinzuzufügenden `IConnectionPointContainerImpl<rowset-name>` und `IRowsetNotifyCP<rowset-name>` der Vererbungskette.  
  
 Hier ist z. B. die Vererbungskette für `RUpdateRowset` in [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Der Beispielcode unterscheiden sich von dem hier aufgeführten ist; den Code sollte wie die aktuelleren Version angesehen werden.  
  
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
  
### <a name="setting-com-map-entries"></a>Festlegen von COM-Zuordnungseinträgen  
 Außerdem müssen Sie die COM-Zuordnung im Rowset Folgendes hinzugefügt:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Diese Makros können bei einem `QueryInterface` für den Verbindungspunktcontainer (die Grundlage für `IRowsetNotify`) auf die angeforderte Schnittstelle für den Anbieter zu suchen. Ein Beispiel zur Verwendung von Verbindungspunkten finden Sie im Beispiel für ATL-POLYGON und Tutorials.  
  
### <a name="setting-connection-point-map-entries"></a>Punkt-Zuordnungseinträge Verbindung festlegen  
 Sie müssen auch eine Verbindung Punkt Karte hinzufügen. Es sollte etwa so aussehen:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Diese Verbindung Punkt Zuordnung kann eine Komponente, die nach der `IRowsetNotify` Schnittstelle in Ihrem Anbieter suchen.  
  
### <a name="setting-properties"></a>Festlegen von Eigenschaften  
 Sie müssen auch die folgenden Eigenschaften an Ihren Anbieter hinzufügen. Sie müssen nur zum Hinzufügen von Eigenschaften, die basierend auf den Schnittstellen, die Sie unterstützen.  
  
|Eigenschaft|Bei Unterstützung hinzufügen|  
|--------------|------------------------|  
|`DBPROP_IConnectionPointContainer`|Immer|  
|`DBPROP_NOTIFICATIONGRANULARITY`|Immer|  
|`DBPROP_NOTIFICATIONPHASES`|Immer|  
|`DBPROP_NOTIFYCOLUMNSET`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWDELETE`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWINSERT`|`IRowsetChange`|  
|`DBPROP_NOTIFYROWSETFETCHPOSITIONCHANGE`|Immer|  
|`DBPROP_NOTIFYROWFIRSTCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWSETRELEASE`|Immer|  
|`DBPROP_NOTIFYROWUNDOCHANGE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDODELETE`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUNDOINSERT`|`IRowsetUpdate`|  
|`DBPROP_NOTIFYROWUPDATE`|`IRowsetUpdate`|  
  
 Den größten Teil der Implementierung für die Benachrichtigungen ist bereits in der OLE DB-Anbietervorlagen eingebettet. Wenn Sie keine hinzufügen `IRowsetNotifyCP` der Vererbungskette der Compiler, diesen gesamten Code aus Ihrem Kompilierung-Datenstrom, wodurch Ihr Code Codegröße entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)