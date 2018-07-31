---
title: CAccessorRowset-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
- CAccessorRowset.Bind
- CAccessorRowset::Bind
- CAccessorRowset::CAccessorRowset
- CAccessorRowset.CAccessorRowset
- CAccessorRowset
- ATL.CAccessorRowset.CAccessorRowset
- ATL::CAccessorRowset::CAccessorRowset
- CAccessorRowset.Close
- CAccessorRowset::Close
- CAccessorRowset::FreeRecordMemory
- CAccessorRowset.FreeRecordMemory
- FreeRecordMemory
- GetColumnInfo
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- CAccessorRowset class
- CAccessorRowset class, methods
- CAccessorRowset class, members
- Bind method
- CAccessorRowset class, constructor
- Close method
- FreeRecordMemory method
- GetColumnInfo method
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: edc18dcb83b2dda63fd5cfb5c56c3c95baa72df0
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340728"
---
# <a name="caccessorrowset-class"></a>CAccessorRowset-Klasse
Kapselt ein Rowset und die zugehörigen Accessoren in einer einzelnen Klasse.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor, 
   template <typename T> class TRowset = CRowset>  
class CAccessorRowset : public TAccessor, public TRowset<TAccessor>  
```  
  
### <a name="parameters"></a>Parameter  
 *TAccessor*  
 Ein Accessor-Klasse.  
  
 *TRowset*  
 Eine Rowset-Klasse.  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Binden](#bind)|Bindungen erstellt (wird verwendet, wenn `bBind` angegeben ist, als **"false"** in [CCommand:: Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](#caccessorrowset)|Konstruktor.|  
|[Schließen](#close)|Schließt das Rowset und alle Accessoren.|  
|[FreeRecordMemory](#freerecordmemory)|Gibt alle Spalten im aktuellen Datensatz, der freigegeben werden müssen frei.|  
|[GetColumnInfo](#getcolumninfo)|Implementiert [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx).|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `TAccessor` verwaltet die Zugriffsmethode. Klasse *TRowset* verwaltet das Rowset.  

## <a name="bind"></a> CAccessorRowset:: Bind
Die Bindungen erstellt, wenn Sie angegeben haben `bBind` als **"false"** in [CCommand:: Open](../../data/oledb/ccommand-open.md).  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Bind();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  

## <a name="caccessorrowset"></a> CAccessorRowset:: CAccessorRowset
Initialisiert das `CAccessorRowset`-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
CAccessorRowset();  
```  

## <a name="close"></a> CAccessorRowset:: Close
Gibt alle aktiven Accessoren und Rowsets frei.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void Close();  
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Arbeitsspeicher frei.  

## <a name="freerecordmemory"></a> CAccessorRowset:: Freerecordmemory
Gibt alle Spalten im aktuellen Datensatz, der freigegeben werden müssen frei.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void FreeRecordMemory();  
```  

## <a name="getcolumninfo"></a> CAccessorRowset:: GetColumnInfo
Ruft die Spalteninformationen aus dem geöffneten Rowset ab.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns, 
   DBCOLUMNINFO** ppColumnInfo, 
   LPOLESTR* ppStrings) const; 
    
HRESULT GetColumnInfo(DBORDINAL* pColumns, 
   DBCOLUMNINFO** ppColumnInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer muss den zurückgegebenen Spalteninformationen und Zeichenfolgenpuffer freigeben. Verwenden Sie die zweite Version dieser Methode, bei der Verwendung [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) und die Bindungen außer Kraft setzen müssen.  
  
 Weitere Informationen finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/library/ms722704.aspx) in die *OLE DB-Programmierreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)