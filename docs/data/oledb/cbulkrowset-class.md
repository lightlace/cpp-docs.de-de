---
title: CBulkRowset-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
- CBulkRowset::AddRefRows
- AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset<TAccessor>.CBulkRowset
- ATL::CBulkRowset::CBulkRowset
- CBulkRowset.CBulkRowset
- CBulkRowset::CBulkRowset
- ATL.CBulkRowset.CBulkRowset
- ATL::CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset<TAccessor>::CBulkRowset
- CBulkRowset
- ATL.CBulkRowset.MoveFirst
- CBulkRowset<TAccessor>.MoveFirst
- ATL.CBulkRowset<TAccessor>.MoveFirst
- ATL::CBulkRowset::MoveFirst
- ATL::CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset::MoveFirst
- CBulkRowset<TAccessor>::MoveFirst
- CBulkRowset.MoveFirst
- CBulkRowset.MoveLast
- ATL.CBulkRowset.MoveLast
- ATL::CBulkRowset<TAccessor>::MoveLast
- CBulkRowset::MoveLast
- CBulkRowset<TAccessor>.MoveLast
- ATL::CBulkRowset::MoveLast
- ATL.CBulkRowset<TAccessor>.MoveLast
- CBulkRowset<TAccessor>::MoveLast
- MoveLast
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
- CBulkRowset::MovePrev
- MovePrev
- CBulkRowset<TAccessor>::MovePrev
- ATL::CBulkRowset<TAccessor>::MovePrev
- CBulkRowset<TAccessor>.MovePrev
- ATL::CBulkRowset::MovePrev
- CBulkRowset.MovePrev
- ATL.CBulkRowset.MovePrev
- ATL.CBulkRowset<TAccessor>.MovePrev
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
- ReleaseRows
- ATL.CBulkRowset<TAccessor>.ReleaseRows
- ATL::CBulkRowset<TAccessor>::ReleaseRows
- ATL.CBulkRowset.ReleaseRows
- CBulkRowset<TAccessor>::ReleaseRows
- ATL::CBulkRowset::ReleaseRows
- CBulkRowset::ReleaseRows
- CBulkRowset.ReleaseRows
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs:
- C++
helpviewer_keywords:
- CBulkRowset class
- AddRefRows method
- CBulkRowset class, constructor
- MoveFirst method
- MoveLast method
- MoveNext method
- MovePrev method
- MoveToBookmark method
- MoveToRatio method
- ReleaseRows method
- SetRows method
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3538a8cd15fc315f4d91d1c83c517811acce1802
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082903"
---
# <a name="cbulkrowset-class"></a>CBulkRowset-Klasse

Abruft und verändert die Zeilen, die auf Daten in einer Massenoperation zu arbeiten, indem mehrere Zeilenhandles mit einem einzigen Aufruf abgerufen.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
### <a name="parameters"></a>Parameter  

*TAccessor*<br/>
Ein Accessor-Klasse.  

## <a name="requirements"></a>Anforderungen  

**Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddRefRows](#addrefrows)|Inkrementiert den Verweiszähler.|  
|[CBulkRowset](#cbulkrowset)|Konstruktor.|  
|[MoveFirst](#movefirst)|Ruft ab, die erste Zeile der Daten, einen neuen Bulk-Abruf bei Bedarf ausführen.|  
|[MoveLast](#movelast)|Wechselt zur letzten Zeile.|  
|[MoveNext](#movenext)|Ruft die nächste Zeile der Daten ab.|  
|[MovePrev](#moveprev)|Wechselt zur vorherigen Zeile.|  
|[MoveToBookmark](#movetobookmark)|Ruft die Zeile, die durch ein Lesezeichen markiert oder auf die Zeile an einem angegebenen Offset aus diesem Lesezeichen ab.|  
|[MoveToRatio](#movetoratio)|Ruft Zeilen ab der ein Bruchteil Ausgangsposition im Rowset ab.|  
|[ReleaseRows](#releaserows)|Legt die aktuelle Zeile (`m_nCurrentRow`) auf 0 (null) und Versionen, die alle Zeilen.|  
|[SetRows](#setrows)|Legt die Anzahl von Zeilenhandles, die von einem Aufruf abgerufen werden sollen.|  
  
## <a name="example"></a>Beispiel  

Das folgende Beispiel veranschaulicht die Verwendung der `CBulkRowset` Klasse.  
  
[!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  

## <a name="addrefrows"></a> CBulkRowset:: Addrefrows

Aufrufe [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619) erhöht den Verweiszähler für alle Zeilen, die derzeit von der Bulk-Rowset abgerufen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT AddRefRows() throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT. 
  
## <a name="cbulkrowset"></a> CBulkRowset:: CBulkRowset

Erstellt ein neues `CBulkRowset` -Objekt und legt die Standardanzahl von Zeilen auf 10.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CBulkRowset();  
```  

## <a name="movefirst"></a> CBulkRowset:: MoveFirst

Ruft die erste Zeile der Daten ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveFirst() throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.

## <a name="movelast"></a> CBulkRowset:: MoveLast

Wechselt zur letzten Zeile.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveLast() throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  

## <a name="movenext"></a> CBulkRowset:: MoveNext

Ruft die nächste Zeile der Daten ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveNext() throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT. Wenn das Ende des Rowsets erreicht wurde, gibt die DB_S_ENDOFROWSET zurück. 

## <a name="moveprev"></a> CBulkRowset:: MovePrev

Wechselt zur vorherigen Zeile.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MovePrev() throw();  
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  

## <a name="movetobookmark"></a> CBulkRowset:: MoveToBookmark

Dadurch wird die Zeile, die durch ein Lesezeichen oder auf die Zeile an einem angegebenen Offset gekennzeichnet (*lSkip*) von diesem Lesezeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark, 
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*Lesezeichen*<br/>
[in] Ein Lesezeichen, markieren den Speicherort, von dem Daten abgerufen werden sollen.  
  
*lSkip*<br/>
[in] Die Anzahl Anzahl von Zeilen aus das Lesezeichen die Zielzeile. Wenn *lSkip* 0 (null), wird die erste Zeile abgerufen wird, den mit Lesezeichen versehenen Zeile. Wenn *lSkip* 1 ist, die erste Zeile abgerufen wird die Zeile nach der Lesezeichen versehenen Zeile. Wenn *lSkip* ist-1. die erste Zeile abgerufen wird die Zeile vor den mit Lesezeichen versehenen Zeile.  
  
### <a name="return-value"></a>Rückgabewert  

Finden Sie unter [IRowset:: GetData](/previous-versions/windows/desktop/ms716988) in die *OLE DB-Programmierreferenz*. 

## <a name="movetoratio"></a> CBulkRowset:: Movetoratio

Ruft Zeilen ab der ein Bruchteil Ausgangsposition im Rowset ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveToRatio(DBCOUNTITEM nNumerator, 
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nNumerator*<br/>
[in] Der Zähler verwendet, um die Sekundenbruchteile Position aus der zum Abrufen von Daten zu bestimmen.  
  
*nDenominator*<br/>
[in] Der Nenner verwendet, um die Sekundenbruchteile Position aus der zum Abrufen von Daten zu bestimmen.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

`MoveToRatio` Ruft die Zeilen ungefähr gemäß der folgenden Formel:  
  
`(nNumerator *  RowsetSize ) / nDenominator`  
  
Wo `RowsetSize` ist die Größe des Rowsets, gemessen in Zeilen. Die Genauigkeit zu dieser Formel hängt von dem Anbieter ab. Weitere Informationen finden Sie unter [IRowsetScroll:: GetRowsAtRatio](/previous-versions/windows/desktop/ms709602) in die *OLE DB-Programmierreferenz*.   

## <a name="releaserows"></a> CBulkRowset:: ReleaseRows

Aufrufe [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771) dekrementiert den Verweiszähler für alle Zeilen, die derzeit von der Bulk-Rowset abgerufen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT ReleaseRows() throw();   
```  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  

## <a name="setrows"></a> CBulkRowset:: setRows

Legt die Anzahl von Zeilenhandles, die von jedem Aufruf abgerufen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void SetRows(DBROWCOUNT nRows) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*nRows*<br/>
[in] Die neue Größe des Rowsets (Anzahl der Zeilen).  
  
### <a name="remarks"></a>Hinweise  

Wenn Sie diese Funktion aufrufen, muss es sein, bevor das Rowset geöffnet wird.
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)