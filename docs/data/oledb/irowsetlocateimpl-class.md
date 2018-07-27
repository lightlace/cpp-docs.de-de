---
title: IRowsetLocateImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
- m_rgBookmarks
- IRowsetLocateImpl::m_rgBookmarks
- ATL.IRowsetLocateImpl.m_rgBookmarks
- ATL::IRowsetLocateImpl::m_rgBookmarks
- IRowsetLocateImpl.m_rgBookmarks
dev_langs:
- C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
- Compare method
- GetRowsAt method
- GetRowsByBookmark method
- Hash method
- m_rgbookmarks
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 986626fa391971ce342f8d80b9e3e7f8ec979b63
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322175"
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl-Klasse
Implementiert die OLE DB [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) -Schnittstelle, die beliebige Zeilen aus einem Rowset abruft.  
  
## <a name="syntax"></a>Syntax

```cpp
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
       T,   
       RowsetInterface,   
       RowClass,   
       MapClass>  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Eine abgeleitete Klasse `IRowsetLocateImpl`.  
  
 *RowsetInterface*  
 Eine abgeleitete Klasse `IRowsetImpl`.  
  
 *RowClass*  
 Die Storage-Einheit für die `HROW`.  
  
 *MapClass*  
 Die Storage-Einheit für alle Zeilenhandles, die vom Anbieter.  
  
 *BookmarkKeyType*  
 Der Typ der Wiederaufnahme des Lesezeichens, z. B. einen Long-Wert oder eine Zeichenfolge. Normale Lesezeichen müssen eine Länge von mindestens zwei Bytes. (Single-Byte-Länge ist für den OLE DB reserviert [standard Lesezeichen](https://msdn.microsoft.com/library/ms712954.aspx)`DBBMK_FIRST`, `DBBMK_LAST`, und `DBBMK_INVALID`.)  
  
 *BookmarkType*  
 Der Zuordnungsmechanismus für die Verwaltung von Lesezeichen-to-Data-Beziehungen.  
  
 *BookmarkMapClass*  
 Die Storage-Einheit für alle Zeilenhandles, die vom Lesezeichen.  

## <a name="requirements"></a>Anforderungen  
 **Header**: atldb.h  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[Compare](#compare)|Vergleicht zwei Lesezeichen.|  
|[GetRowsAt](#getrowsat)|Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.|  
|[GetRowsByBookmark](#getrowsbybookmark)|Ruft die Zeilen, die die angegebenen Lesezeichen entsprechen.|  
|[Hash](#hash)|Gibt hash-Werte für den angegebenen Lesezeichen.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_rgBookmarks](#rgbookmarks)|Ein Array von Lesezeichen.|  
  
## <a name="remarks"></a>Hinweise  
 `IRowsetLocateImpl` ist die Implementierung der OLE DB-Vorlagen von den [IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx) Schnittstelle. `IRowsetLocate` wird verwendet, um beliebige Zeilen aus einem Rowset abzurufen. Ein Rowset, das diese Schnittstelle nicht implementiert ist eine `sequential` Rowset. Wenn `IRowsetLocate` vorhanden ist für ein Rowset, ist die Spalte 0 das Lesezeichen für die Zeilen, lesen diese Spalte erhält einen Lesezeichenwert, der mit dem in der gleichen Zeile positioniert werden kann.  
  
 `IRowsetLocateImpl` wird verwendet, um lesezeichenunterstützung in Anbietern zu implementieren. Lesezeichen sind Platzhalter (Indizes für ein Rowset), mit die den Consumer schnell zu einer Zeile zurückkehren können schnelle Zugriff auf Daten gewährt. Der Anbieter bestimmt, wie Lesezeichen eindeutig können eine Zeile zu identifizieren. Mithilfe von `IRowsetLocateImpl` Methoden, Sie können Lesezeichen vergleichen, Fetch Zeilen durch die Werte für offset, Fetch-Zeilen durch Lesezeichen, und der Hashwerte für Lesezeichen zurückzugeben.  
  
 Stellen Sie zur Unterstützung von OLE DB-Lesezeichen in einem Rowset, das Rowset, das von dieser Klasse erben.  
  
 Informationen zum Implementieren der lesezeichenunterstützung finden Sie unter [-Anbieter unterstützt Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md) in die *Visual C++ Handbuch für Programmierer* und [Lesezeichen](https://msdn.microsoft.com/library/ms709728.aspx) in die *OLE DB-Programmierreferenz* im Platform SDK.  

## <a name="compare"></a> IRowsetLocateImpl:: Compare
Vergleicht zwei Lesezeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Compare )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetLocate::Compare](https://msdn.microsoft.com/library/ms709539.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Eine der Lesezeichen können ein Standard werden OLE DB-definierten [standard Lesezeichen](https://msdn.microsoft.com/library/ms712954.aspx) (`DBBMK_FIRST`, `DBBMK_LAST`, oder `DBBMK_INVALID`). Der zurückgegebene Wert in `pComparison` gibt die Beziehung zwischen zwei Lesezeichen:  
  
-   DBCOMPARE_LT (`cbBookmark1` ist, bevor Sie `cbBookmark2`.)  
  
-   DBCOMPARE_EQ (`cbBookmark1` gleich `cbBookmark2`.)  
  
-   DBCOMPARE_GT (`cbBookmark1` ist nach `cbBookmark2`.)  
  
-   DBCOMPARE_NE (Lesezeichen sind gleich und nicht sortiert.)  
  
-   DBCOMPARE_NOTCOMPARABLE (Lesezeichen können nicht verglichen werden.) 

## <a name="getrowsat"></a> IRowsetLocateImpl:: GetRowsAt
Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetRowsAt )(HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetLocate:: GetRowsAt](https://msdn.microsoft.com/library/ms723031.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Um stattdessen von der Cursorposition bis zu abzurufen, verwenden Sie [IRowset::GetRowsAt](https://msdn.microsoft.com/library/ms723031.aspx).  
  
 `IRowsetLocateImpl::GetRowsAt` die Position des Cursors wird nicht geändert werden. 

## <a name="getrowsbybookmark"></a> IRowsetLocateImpl:: Getrowsbybookmark
Ruft eine oder mehrere Zeilen, die die angegebenen Lesezeichen entsprechen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const DBBKMARK rgcbBookmarks[],  
   const BYTE* rgpBookmarks,  
   HROW rghRows[],  
   DBROWSTATUS* rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht *hChapter* Parameter [IRowsetLocate:: Getrowsbybookmark](https://msdn.microsoft.com/library/ms725420.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetLocate:: Getrowsbybookmark](https://msdn.microsoft.com/library/ms725420.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Das Lesezeichen kann ein Wert, die Sie definieren oder eine OLE DB sein [standard Lesezeichen](https://msdn.microsoft.com/library/ms712954.aspx) (`DBBMK_FIRST` oder `DBBMK_LAST`). Die Position des Cursors wird nicht geändert werden.  

## <a name="hash"></a> IRowsetLocateImpl:: Hash
Gibt hash-Werte für den angegebenen Lesezeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 *hReserved*  
 [in] Entspricht *hChapter* Parameter [IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetLocate::Hash](https://msdn.microsoft.com/library/ms709697.aspx) in die *OLE DB-Programmierreferenz*.  

## <a name="rgbookmarks"></a> IRowsetLocateImpl:: M_rgbookmarks
Ein Array von Lesezeichen.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CAtlArray<DBROWCOUNT> m_rgBookmarks;  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbieter](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/library/ms721190.aspx)   
 [Anbieterunterstützung für Lesezeichen](../../data/oledb/provider-support-for-bookmarks.md)   
 [BTextmarken](https://msdn.microsoft.com/library/ms709728.aspx)
