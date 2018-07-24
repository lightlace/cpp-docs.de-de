---
title: CArrayRowset-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b367fc74fdbb03a6e5193f3fc9be08f74111a09
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207486"
---
# <a name="carrayrowset-class"></a>CArrayRowset-Klasse
Greift auf die Elemente eines Rowsets mit Arraysyntax.  
  
## <a name="syntax"></a>Syntax

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
### <a name="parameters"></a>Parameter  
 *TAccessor*  
 Der Typ der Accessor-Klasse, die Sie auf das Rowset verwenden möchten.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CArrayRowset](#carrayrowset)|Konstruktor.|  
|[Snapshot](#snapshot)|Liest das gesamte Rowset in den Speicher an.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator&#91;&#93;](#operator)|Greift auf ein Element des Rowsets.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](#nrowsread)|Die Anzahl der Zeilen, die bereits gelesen.|  
  
## <a name="carrayrowset"></a> CArrayRowset:: CArrayRowset
Erstellt ein neues `CArrayRowset`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      CArrayRowset(int nMax = 100000);  
```  
  
#### <a name="parameters"></a>Parameter  
 *nmax.*  
 [in] Maximale Anzahl von Zeilen im Rowset. 

## <a name="snapshot"></a> CArrayRowset:: Snapshot
Liest das gesamte Rowset in den Speicher, erstellen ein Bild oder eine Momentaufnahme davon.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Snapshot() throw();  
  
```  

## <a name="operator"></a> CArrayRowset:: Operator
Stellt arrayähnlichen Syntax für den Zugriff auf eine Zeile im Rowset bereit.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Parameter  
 *TAccessor*  
 Auf Vorlagen basierenden Parameter, der den Typ des Accessors gespeichert, in dem Rowset angibt.  
  
 *Funktionen "nrow"*  
 [in] Anzahl von der Zeile (Arrayelement), die Sie zugreifen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Inhalt der die angeforderte Zeile.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *Funktionen "nrow"* überschreitet die Anzahl der Zeilen im Rowset, wird eine Ausnahme ausgelöst.  

## <a name="nrowsread"></a> CArrayRowset:: M_nrowsread
Enthält die Anzahl der Zeilen im Rowset, die bereits gelesen wurden.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
ULONG m_nRowsRead;  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset-Klasse](../../data/oledb/crowset-class.md)