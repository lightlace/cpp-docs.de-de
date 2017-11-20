---
title: IRowsetNotifyCP-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetNotifyCP
dev_langs: C++
helpviewer_keywords: IRowsetNotifyCP class
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1d110b3bc304664681532ae7511a9e886a05058b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP-Klasse
Die Anbieter-Website für die Verbindungspunkt-Schnittstelle implementiert [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse `IRowsetNotifyCP`.  
  
 `ReentrantEventSync`  
 Ein Mutex-Klasse, die Reentranz unterstützt (die Standardeinstellung ist **CComSharedMutex**). Ein Mutex wird ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.  
  
 `piid`  
 Ein Schnittstellenzeiger-ID (**IID\***) für eine **IRowsetNotify** Verbindungspunkt-Schnittstelle. Der Standardwert ist **& __uuidof(IRowsetNotify)**.  
  
 `DynamicUnkArray`  
 Ein Array vom Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), also ein dynamisch zugeordnetes Arrays von **IUnknown** Zeiger an den Client sink-Schnittstellen.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Fire_OnFieldChange](../../data/oledb/irowsetnotifycp-fire-onfieldchange.md)|Benachrichtigt den Consumer eine Änderung auf den Wert einer Spalte an.|  
|[Fire_OnRowChange](../../data/oledb/irowsetnotifycp-fire-onrowchange.md)|Benachrichtigt den Consumer eine Änderung der Auswirkungen auf die Zeilen an.|  
|[Fire_OnRowsetChange](../../data/oledb/irowsetnotifycp-fire-onrowsetchange.md)|Den Consumer eine Änderung der Auswirkungen auf das gesamte Rowset wird benachrichtigt.|  
  
## <a name="remarks"></a>Hinweise  
 `IRowsetNotifyCP`implementiert broadcast Funktionen, um die advise-Listener auf dem Verbindungspunkt **IID_IRowsetNotify** Änderungen an den Inhalt des Rowsets.  
  
 Beachten Sie, die Sie implementieren und registrieren Außerdem müssen `IRowsetNotify` auf Consumer (auch bekannt als "Senke" genannt) mit [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , damit der Consumer Benachrichtigungen behandeln kann. Finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) zum Implementieren der Verbindungspunkt-Schnittstelle für den Consumer.  
  
 Ausführliche Informationen zum Implementieren von Benachrichtigungen finden Sie unter "Benachrichtigungen unterstützen" im [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Benachrichtigungen (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)