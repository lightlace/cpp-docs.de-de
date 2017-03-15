---
title: "Unterst&#252;tzen von Benachrichtigungen | Microsoft Docs"
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
  - "Benachrichtigungen [C++], OLE DB-Consumer"
  - "OLE DB-Consumer, Benachrichtigungen"
  - "OLE DB-Anbietervorlagen, Benachrichtigungen"
  - "OLE DB-Anbieter, Benachrichtigungen"
  - "Rowsets, Ereignisbenachrichtigungen"
ms.assetid: 76e875fd-2bfd-4e4e-9f43-dbe5a3fa7382
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Unterst&#252;tzen von Benachrichtigungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Implementieren von Verbindungspunkt\-Schnittstellen für Anbieter und Consumer  
 Damit Benachrichtigungen implementiert werden können, muss eine Anbieterklasse von [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md) und [IConnectionPointContainer](../../atl/reference/iconnectionpointcontainerimpl-class.md) erben.  
  
 Durch `IRowsetNotifyCP` wird die Anbietersite für die Verbindungspunkt\-Schnittstelle [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) implementiert.  `IRowsetNotifyCP` implementiert Übertragungsfunktionen, mit denen Listener am **IID\_IRowsetNotify**\-Verbindungspunkt informiert werden, dass der Inhalt des Rowsets geändert wurde.  
  
 Beachten Sie, dass zusätzlich `IRowsetNotify` \(wird auch als Senke bezeichnet\) mithilfe von [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) für den Consumer implementiert und registriert werden muss, damit Benachrichtigungen vom Consumer behandelt werden können.  Informationen zum Implementieren der Verbindungspunkt\-Schnittstelle für den Consumer finden Sie unter [Empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md).  
  
 Außerdem muss die Klasse eine Zuordnung enthalten, in der der Verbindungspunkteintrag, wie im Folgenden dargestellt, definiert ist:  
  
```  
BEGIN_CONNECTION_POINT_MAP  
   CONNECTIONPOINT_ENTRY (IID_IRowsetNotify)  
END_CONNECTION_POINT_MAP  
```  
  
## Hinzufügen von "IRowsetNotify"  
 Zum Hinzufügen von `IRowsetNotify` müssen `IConnectionPointContainerImpl<rowset-name>` und `IRowsetNotifyCP<rowset-name>` in die Vererbungskette eingefügt werden.  
  
 Als Beispiel sehen Sie hier die Vererbungskette für `RUpdateRowset` aus [UpdatePV](assetId:///c8bed873-223c-4a7d-af55-f90138c6f38f):  
  
> [!NOTE]
>  Der Beispielcode kann von dem hier aufgeführten Code abweichen, sollte jedoch als aktuellere Version angesehen werden.  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
  
class RUpdateRowset :   
public CRowsetImpl< RUpdateRowset, CAgentMan, CUpdateCommand,   
         CAtlArray< CAgentMan, CAtlArray<CAgentMan> >, CSimpleRow,   
         IRowsetScrollImpl< RUpdateRowset, IRowsetScroll > >,  
      public IRowsetUpdateImpl< RUpdateRowset, CAgentMan >,  
      public IConnectionPointContainerImpl<RUpdateRowset>,  
      public IRowsetNotifyCP<RUpdateRowset>  
```  
  
### Festlegen von Einträgen in der COM\-Zuordnung  
 Der COM\-Zuordnung im Rowset müssen außerdem folgende Makros hinzugefügt werden:  
  
```  
COM_INTERFACE_ENTRY(IConnectionPointContainer)  
COM_INTERFACE_ENTRY_IMPL(IConnectionPointContainer)  
```  
  
 Mithilfe dieser Makros kann bei einem `QueryInterface`\-Aufruf für den Verbindungspunktcontainer \(die Basis für `IRowsetNotify`\) stets die angeforderte Schnittstelle aus dem Anbieter ermittelt werden.  Informationen zur Verwendung von Verbindungspunkten finden Sie im ATL POLYGON\-Beispiel und \-Lernprogramm.  
  
### Festlegen von Einträgen in der Verbindungspunktzuordnung  
 Sie müssen außerdem eine Verbindungspunktzuordnung hinzufügen,  die in etwa mit der folgenden vergleichbar ist:  
  
```  
BEGIN_CONNECTION_POINT_MAP(rowset-name)  
     CONNECTION_POINT_ENTRY(_uuidof(IRowsetNotify))  
END_CONNECTION_POINT_MAP()  
```  
  
 Durch die Verbindungspunktzuordnung kann eine Komponente, die die `IRowsetNotify`\-Schnittstelle sucht, diese Schnittstelle im Anbieter auffinden.  
  
### Festlegen von Eigenschaften  
 Dem Anbieter müssen darüber hinaus die folgenden Eigenschaften hinzugefügt werden.  Es müssen nur Eigenschaften auf der Grundlage der unterstützten Schnittstellen hinzugefügt werden.  
  
|Eigenschaft|Bei Unterstützung hinzufügen|  
|-----------------|----------------------------------|  
|**DBPROP\_IConnectionPointContainer**|Immer|  
|**DBPROP\_NOTIFICATIONGRANULARITY**|Immer|  
|**DBPROP\_NOTIFICATIONPHASES**|Immer|  
|**DBPROP\_NOTIFYCOLUMNSET**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWDELETE**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWINSERT**|`IRowsetChange`|  
|**DBPROP\_NOTIFYROWSETFETCHPOSITIONCHANGE**|Immer|  
|**DBPROP\_NOTIFYROWFIRSTCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWSETRELEASE**|Immer|  
|**DBPROP\_NOTIFYROWUNDOCHANGE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDODELETE**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUNDOINSERT**|`IRowsetUpdate`|  
|**DBPROP\_NOTIFYROWUPDATE**|`IRowsetUpdate`|  
  
 Die meisten Implementierungsfunktionen für Benachrichtigungen sind bereits in die OLE DB\-Anbietervorlagen eingebettet.  Wenn `IRowsetNotifyCP` der Vererbungskette nicht hinzugefügt wird, entfernt der Compiler aufgrund eines Compilerfeatures in Visual C\+\+.NET den gesamten Code aus dem Kompilierungsstream, wodurch die Codegröße reduziert wird.  
  
## Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)