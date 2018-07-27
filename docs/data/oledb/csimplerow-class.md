---
title: CSimpleRow-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- CSimpleRow
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
dev_langs:
- C++
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7f37390b4ab5db4cb3b519c801052c4b02102af6
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269795"
---
# <a name="csimplerow-class"></a>CSimpleRow-Klasse
Stellt eine Standardimplementierung für den Zeilenziehpunkt, die in dient der [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax

```cpp
class CSimpleRow  
```  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  

## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRow](#addrefrow)|Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.|  
|[Compare](#compare)|Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.|  
|[CSimpleRow](#csimplerow)|Der Konstruktor.|  
|[ReleaseRow](#releaserow)|Gibt Zeilen frei.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_dwRef](#dwref)|Der Verweiszähler auf einem vorhandenen Zeilenhandle.|  
|[m_iRowset](#irowset)|Ein Index in das Rowset, der den Cursor darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile. `IRowsetImpl` erstellt ein neues `CSimpleRow` für jede Zeile im angeforderten [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md). `CSimpleRow` kann auch durch eine eigene Implementierung von den Zeilenziehpunkt, ersetzt werden, wie ein Standardvorlagenargument zu `IRowsetImpl`. Die einzige Voraussetzung für diese Klasse zu ersetzen ist, damit die äquivalente Klasse einen Konstruktor bereit, der einen einzelnen Parameter vom Typ akzeptiert **lange**.  

## <a name="addrefrow"></a> Csimplerow:: Addrefrow
Fügt einen Verweiszähler auf einem vorhandenen Zeilenhandle auf threadsichere Weise.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DWORD AddRefRow();  
  
```  

## <a name="compare"></a> Csimplerow:: Compare
Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pRow*  
 Ein Zeiger auf eine `CSimpleRow` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein HRESULT-Wert, in der Regel S_OK, der angibt, die zwei Zeilen sind die gleiche Zeileninstanz oder S_FALSE, der angibt, der zwei Zeilen sind unterschiedlich. Finden Sie unter [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/library/ms719629.aspx) in die *OLE DB-Programmierreferenz* für weitere mögliche Rückgabewerte. 

## <a name="csimplerow"></a> Csimplerow:: Csimplerow
Der Konstruktor.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      CSimpleRow(DBCOUNTITEM iRowsetCur);  
```  
  
#### <a name="parameters"></a>Parameter  
 *iRowsetCur*  
 [in] Indizieren Sie auf das aktuelle Rowset.  
  
### <a name="remarks"></a>Hinweise  
 Legt [M_iRowset](../../data/oledb/csimplerow-m-irowset.md) zu *iRowsetCur*. 

## <a name="releaserow"></a> Csimplerow:: Releaserow
Gibt die Zeilen in einer threadsicheren Weise frei.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DWORD ReleaseRow();  
  
```  

## <a name="dwref"></a> Csimplerow:: M_dwref
Der Verweiszähler auf einem vorhandenen Zeilenhandle.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
DWORD m_dwRef;  
  
```  

## <a name="irowset"></a> Csimplerow:: M_irowset
Indizieren Sie auf das Rowset, der den Cursor darstellt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
KeyType m_iRowset;  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)
