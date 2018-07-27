---
title: IRowsetUpdateImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
dev_langs:
- C++
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d58709e9a2b5bd86102e8323456c6bf9ca72fa1
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322136"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl-Klasse
Die OLE DB-Vorlagen-Implementierung, der die [IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  

class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Eine abgeleitete Klasse `IRowsetUpdateImpl`.  
  
 *Speicher*  
 Der Benutzerdatensatz.  
  
 *UpdateArray*  
 Ein Array mit zwischengespeicherten Daten für das Rowset zu aktualisieren.  
  
 *RowClass*  
 Die Storage-Einheit für die `HROW`.  
  
 *MapClass*  
 Die Storage-Einheit für alle Zeilenhandles, die vom Anbieter.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods-used-with-irowsetchange"></a>Schnittstellenmethoden (mit IRowsetChange verwendet)  
  
|||  
|-|-|  
|[SetData](#setdata)|Legt Datenwerte in einer oder mehreren Spalten fest.|  
  
### <a name="interface-methods-used-with-irowsetupdate"></a>Schnittstellenmethoden (mit IRowsetUpdate verwendet)  
  
|||  
|-|-|  
|[GetOriginalData](#getoriginaldata)|Ruft die Daten zuletzt übertragen oder abgerufen, die aus der Datenquelle, die ausstehende Änderungen werden ignoriert.|  
|[GetPendingRows](#getpendingrows)|Gibt eine Liste der Zeilen mit ausstehenden Änderungen.|  
|[GetRowStatus](#getrowstatus)|Der Status der angegebenen Zeilen zurückgegeben.|  
|[Rückgängig machen](#undo)|Macht alle Änderungen auf die Zeile seit der letzten Fetch oder aktualisieren.|  
|[Update (Aktualisieren)](#update)|Überträgt alle Änderungen, die auf die Zeile seit der letzten Fetch oder aktualisieren.|  
  
### <a name="implementation-methods-callback"></a>Implementierungsmethoden (Rückruf)  
  
|||  
|-|-|  
|[IsUpdateAllowed](#isupdateallowed)|Zum verwendet überprüfen und so weiter für die Sicherheit, Integrität, bevor Sie Updates zulassen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_mapCachedData](#mapcacheddata)|Enthält die ursprünglichen Daten für die verzögerte Ausführung.|  
  
## <a name="remarks"></a>Hinweise  
 Sie sollten zuerst lesen und verstehen Sie die Dokumentation für [IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx), da alles, was wird beschrieben, auch hier gilt. Lesen Sie auch im Kapitel 6 die *OLE DB-Programmierreferenz* zum Festlegen von Daten.  
  
 `IRowsetUpdateImpl` implementiert die OLE DB `IRowsetUpdate` -Schnittstelle, die Consumer die Übertragung von Änderungen mit Verzögerung ermöglicht `IRowsetChange` auf die Datenquelle und die Änderungen vor der Übertragung rückgängig zu machen.  
  
> [!IMPORTANT]
>  Es wird dringend empfohlen, bevor Sie versuchen, Ihren Anbieter implementiert die folgende Dokumentation zu lesen:  
  
-   [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Kapitel 6, der die *OLE DB-Programmierreferenz*  
  
-   Siehe auch die `RUpdateRowset` Klasse wird verwendet, in dem Beispiel UpdatePV  

## <a name="setdata"></a> IRowsetUpdateImpl:: SetData
Legt Datenwerte in einer oder mehreren Spalten fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetChange:: SetData](https://msdn.microsoft.com/library/ms721232.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [IRowsetChangeImpl:: SetData](../../data/oledb/irowsetchangeimpl-setdata.md) Methode enthält jedoch die Zwischenspeicherung von ursprünglichen Daten, um entweder sofort oder verzögerte Verarbeitung des Vorgangs zu ermöglichen.

## <a name="getoriginaldata"></a> IRowsetUpdateImpl:: Getoriginaldata
Ruft die Daten zuletzt übertragen oder abgerufen, die aus der Datenquelle, die ausstehende Änderungen werden ignoriert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetOriginalData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/library/ms709947.aspx) in die *OLE DB-Programmierreferenz*.   

## <a name="getpendingrows"></a> IRowsetUpdateImpl:: Getpendingrows
Gibt eine Liste der Zeilen mit ausstehenden Änderungen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht der *hChapter* Parameter im [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/library/ms719626.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="getrowstatus"></a> IRowsetUpdateImpl:: GetRowStatus
Der Status der angegebenen Zeilen zurückgegeben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBPENDINGSTATUS rgPendingStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht der *hChapter* Parameter im [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/library/ms724377.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="undo"></a> IRowsetUpdateImpl:: Undo
Macht alle Änderungen auf die Zeile seit der letzten Fetch oder aktualisieren.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht der *hChapter* Parameter im [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *pcRowsUndone*  
 [out] Entspricht der *PcRows* Parameter im [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 *prgRowsUndone*  
 [in] Entspricht der *PrgRows* Parameter im [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate::Undo](https://msdn.microsoft.com/library/ms719655.aspx) in die *OLE DB-Programmierreferenz*. 

## <a name="update"></a> IRowsetUpdateImpl:: Update
Überträgt alle Änderungen, die auf die Zeile seit der letzten Fetch oder aktualisieren.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht der *hChapter* Parameter im [IRowsetUpdate:: Update](https://msdn.microsoft.com/library/ms719709.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate:: Update](https://msdn.microsoft.com/library/ms719709.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Änderungen werden durch den Aufruf übertragen [IRowsetChangeImpl:: FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Der Consumer muss Aufrufen [CRowset:: Update](../../data/oledb/crowset-update.md) für die Änderungen wirksam werden. Legen Sie *PrgRowstatus* auf einen geeigneten Wert wie beschrieben in [Zeilenstatus](https://msdn.microsoft.com/library/ms722752.aspx) in die *OLE DB-Programmierreferenz*. 
  
## <a name="isupdateallowed"></a> IRowsetUpdateImpl:: IsUpdateAllowed
Überschreiben Sie diese Methode zu prüfen, Sicherheit, Integrität und so weiter vor Updates.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Parameter  
 *status*  
 [in] Der Status der ausstehenden Vorgänge für die Zeilen.  
  
 *hRowUpdate*  
 [in] Handle für die Zeilen, die der Benutzer aktualisieren möchte.  
  
 *pRowStatus*  
 [out] Der Status an den Benutzer zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie feststellen, dass ein Update zugelassen werden soll, gibt S_OK zurück. Andernfalls wird E_FAIL zurückgegeben. Wenn Sie eine Aktualisierung zu ermöglichen, müssen Sie auch zum Festlegen der `DBROWSTATUS` in [IRowsetUpdateImpl:: Update](../../data/oledb/irowsetupdateimpl-update.md) auf einen entsprechenden [Zeilenstatus](https://msdn.microsoft.com/library/ms722752.aspx).  

## <a name="mapcacheddata"></a> IRowsetUpdateImpl:: M_mapcacheddata
Eine Karte mit den ursprünglichen Daten für die verzögerte Ausführung.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### <a name="parameters"></a>Parameter  
 *hRow*  
 Handle für die Zeilen für die Daten.  
  
 *pData*  
 Ein Zeiger auf die Daten zwischengespeichert werden. Die Daten sind vom Typ *Storage* (die Benutzerdatensatz-Klasse). Finden Sie unter den *Storage* Vorlagenargument in [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md).  

## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Erstellen eines aktualisierbaren Anbieters](../../data/oledb/creating-an-updatable-provider.md)
