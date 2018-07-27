---
title: IColumnsInfoImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
dev_langs:
- C++
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1aa70a8efea82660632cf0219c76009eea44f606
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269812"
---
# <a name="icolumnsinfoimpl-class"></a>IColumnsInfoImpl-Klasse
Stellt eine Implementierung der [IColumnsInfo](https://msdn.microsoft.com/library/ms724541.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IColumnsInfoImpl`.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](#getcolumninfo)|Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.|  
|[MapColumnIDs](#mapcolumnids)|Gibt ein Array von Ordnungszahlen der Spalten in einem Rowset, das durch die angegebenen Spalten-IDs gekennzeichnet sind.|  
  
## <a name="remarks"></a>Hinweise  
 Eine erforderliche Schnittstelle für Rowsets und Befehle. So ändern Sie das Verhalten Ihres Anbieters `IColumnsInfo` Implementierung müssen Sie die Anbieter-Spalte-Zuordnung zu ändern.  

## <a name="getcolumninfo"></a> Icolumnsinfoimpl:: GetColumnInfo
Gibt die von den meisten Consumern benötigte Spaltenmetadaten zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,  
   DBCOLUMNINFO** prgInfo,  
   OLECHAR** ppStringsBuffer);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="mapcolumnids"></a> Icolumnsinfoimpl:: Mapcolumnids
Gibt ein Array von Ordnungszahlen der Spalten in einem Rowset, das durch die angegebenen Spalten-IDs gekennzeichnet sind.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,  
   const DBID rgColumnIDs[],  
   DBORDINAL rgColumns[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IColumnsInfo::MapColumnIDs](https://msdn.microsoft.com/library/ms714200.aspx) in die *OLE DB-Programmierreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
