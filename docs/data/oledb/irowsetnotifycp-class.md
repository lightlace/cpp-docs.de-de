---
title: IRowsetNotifyCP-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP
- Fire_OnFieldChange
- ATL::IRowsetNotifyCP::Fire_OnFieldChange
- ATL.IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnFieldChange
- IRowsetNotifyCP::Fire_OnFieldChange
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
- Fire_OnRowsetChange
- IRowsetNotifyCP::Fire_OnRowsetChange
- IRowsetNotifyCP.Fire_OnRowsetChange
- ATL::IRowsetNotifyCP::Fire_OnRowsetChange
- ATL.IRowsetNotifyCP.Fire_OnRowsetChange
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyCP class
- Fire_OnFieldChange method
- Fire_OnRowChange method
- Fire_OnRowsetChange method
ms.assetid: ccef402b-94a0-4c2e-9a13-7e854ef82390
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 207128da3e46da492ebc812b68d9ef09847045e5
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322123"
---
# <a name="irowsetnotifycp-class"></a>IRowsetNotifyCP-Klasse
Die Website für die Verbindungspunkt-Schnittstelle implementiert [IRowsetNotify](https://msdn.microsoft.com/library/ms712959.aspx).  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class ReentrantEventSync = CComSharedMutex>  
class IRowsetNotifyCP :   
   public IConnectionPointImpl<  
      T,   
      piid = &__uuidof(IRowsetNotify),   
      CComDynamicUnkArray DynamicUnkArray>,  
   public ReentrantEventSync  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Eine abgeleitete Klasse `IRowsetNotifyCP`.  
  
 *ReentrantEventSync*  
 Ein Mutex-Klasse, die Eintrittsinvarianz unterstützt (die Standardeinstellung ist `CComSharedMutex`). Ein Mutex ist ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.  
  
 *piid*  
 Ein ID-Schnittstellenzeiger (`IID*`) für eine `IRowsetNotify` Verbindungspunkt-Schnittstelle. Der Standardwert ist `&__uuidof(IRowsetNotify)`.  
  
 *DynamicUnkArray*  
 Ein Array vom Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), d.h. ein dynamisch zugeordnetes Array aus `IUnknown` sink-Schnittstellen Zeigern auf dem Client. 

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“   
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Fire_OnFieldChange](#onfieldchange)|Benachrichtigt den Consumer über eine Änderung an den Wert einer Spalte.|  
|[Fire_OnRowChange](#onrowchange)|Benachrichtigt den Consumer über eine Änderung, die Auswirkungen auf die Zeilen.|  
|[Fire_OnRowsetChange](#onrowsetchange)|Benachrichtigt den Consumer über eine Änderung, die Auswirkungen auf das gesamte Rowset.|  
  
## <a name="remarks"></a>Hinweise  
 `IRowsetNotifyCP` broadcast-implementiert Funktionen, um den Listener auf dem Verbindungspunkt empfehlen `IID_IRowsetNotify` von Änderungen an den Inhalt des Rowsets.  
  
 Beachten Sie, dass Sie auch implementieren registrieren müssen `IRowsetNotify` vom Consumer (auch bekannt als "Senke" genannt) mit [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) , damit der Consumer mit Benachrichtigungen behandeln kann. Finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) zur Implementierung der vom Consumer der Verbindungspunkt-Schnittstelle.  
  
 Ausführliche Informationen zum Implementieren von Benachrichtigungen finden Sie unter "Unterstützen von Benachrichtigungen" in [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md).  

## <a name="onfieldchange"></a> IRowsetNotifyCP:: Fire_onfieldchange
Überträgt ein [OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) Ereignis benachrichtigt Kunden über eine Änderung an den Wert einer Spalte.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Fire_OnFieldChange(IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/library/ms715961.aspx) in die *OLE DB-Programmierreferenz*. 

## <a name="onrowchange"></a> IRowsetNotifyCP:: Fire_onrowchange
Überträgt ein [OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) Ereignis an alle Listener für den Verbindungspunkt `IID_IRowsetNotify` benachrichtigen Kunden über eine Änderung, die Auswirkungen auf die Zeilen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/library/ms722694.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="onrowsetchange"></a> IRowsetNotifyCP:: Fire_onrowsetchange
Überträgt ein [OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) Ereignis an alle Listener für den Verbindungspunkt `IID_IRowsetNotify` benachrichtigen Kunden über eine Änderung, die Auswirkungen auf das gesamte Rowset.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Fire_OnRowsetChange(IRowset* pRowset,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/library/ms722669.aspx) in die *OLE DB-Programmierreferenz*.
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Benachrichtigungen (COM)](http://msdn.microsoft.com/library/windows/desktop/ms678433)   
 [BEGIN_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#begin_connection_point_map)   
 [END_CONNECTION_POINT_MAP](../../atl/reference/connection-point-macros.md#end_connection_point_map)   
 [CONNECTION_POINT_ENTRY](../../atl/reference/connection-point-macros.md#connection_point_entry)   
 [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)
