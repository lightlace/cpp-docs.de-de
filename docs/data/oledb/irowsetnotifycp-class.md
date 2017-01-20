---
title: "IRowsetNotifyCP-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetNotifyCP-Klasse"
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyCP-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Anbietersite für die Verbindungspunkt\-Schnittstelle [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## Syntax  
  
```  
template <  
   class T,   
   class ReentrantEventSync = CComSharedMutex   
>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray  
   >,  
   public ReentrantEventSync  
```  
  
#### Parameter  
 `T`  
 Eine Klasse wird von `IRowsetNotifyCP` abgeleitet.  
  
 `ReentrantEventSync`  
 Eine Mutexklasse, die Reentranz unterstützt \(Standardeinstellung, **CComSharedMutex** ist\).  Ein Mutex ist ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource.  
  
 `piid`  
 Ein Schnittstellen\-ID\-Zeiger \(**IID\***\) für eine **IRowsetNotify**  Verbindungspunkt\-Schnittstelle.  Der Standardwert ist **&\_\_uuidof\(IRowsetNotify\)**.  
  
 `DynamicUnkArray`  
 Ein Array Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), der ein Array dynamisch zugeordnete **IUnknown** Zeiger auf den Clientsenkenschnittstellen ist.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Fire\_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Benachrichtigt den Consumer zu einer Änderung am Wert einer Spalte.|  
|[Fire\_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Benachrichtigt den Consumer zu einer Änderung, die die Zeilen angewendet.|  
|[Fire\_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Benachrichtigt den Consumer zu einer Änderung, die das gesamte Rowset beeinflusst.|  
  
## Hinweise  
 `IRowsetNotifyCP` implementiert Übertragungsfunktionen, mit denen Listener am **IID\_IRowsetNotify**\-Verbindungspunkt informiert werden, dass der Inhalt des Rowsets geändert wurde.  
  
 Beachten Sie, dass Sie `IRowsetNotify` für den Consumer \(auch als Senke ""\) mit [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) auch implementiert und registriert werden muss, damit Benachrichtigungen vom Consumer behandelt werden können.  Siehe [Empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) über das Implementieren des Verbindungspunkts, für den Consumer herzustellen.  
  
 Ausführliche Informationen zum Implementieren der Benachrichtigungen, finden Sie unter "Determining Unterstützen von Benachrichtigungen" in [Erstellen für einen aktualisierbaren Anbieter](../../data/oledb/creating-an-updatable-provider.md).  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Notifications \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [Overview of Notifications \(OLE DB\)](https://msdn.microsoft.com/en-us/library/ms725406.aspx)   
 [BEGIN\_CONNECTION\_POINT\_MAP](../Topic/BEGIN_CONNECTION_POINT_MAP.md)   
 [END\_CONNECTION\_POINT\_MAP](../Topic/END_CONNECTION_POINT_MAP.md)   
 [CONNECTION\_POINT\_ENTRY](../Topic/CONNECTION_POINT_ENTRY.md)   
 [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)