---
title: 'CRowset:: MoveToBookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRowset::MoveToBookmark
- ATL::CRowset<TAccessor>::MoveToBookmark
- ATL.CRowset.MoveToBookmark
- ATL.CRowset<TAccessor>.MoveToBookmark
- MoveToBookmark
- CRowset::MoveToBookmark
- CRowset.MoveToBookmark
- CRowset<TAccessor>::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9f638f928c9fee0383e5ed50cd4b3dd547ad4939
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetmovetobookmark"></a>CRowset::MoveToBookmark
Dadurch wird die Zeile markiert ein Lesezeichen bzw. die Zeile mit einem angegebenen Offset (`lSkip`) von diesem Lesezeichen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,   
   LONG lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `bookmark`  
 [in] Ein Lesezeichen, markieren den Speicherort, aus dem Daten abgerufen werden sollen.  
  
 `lSkip`  
 [in] Die Anzahl Anzahl von Zeilen aus das Lesezeichen Zielzeile. Wenn `lSkip` NULL ist, wird die erste Zeile abgerufen wird, dem Lesezeichen versehenen Zeile. Wenn `lSkip` 1, ist die erste Zeile abgerufen wird die Zeile nach dem Lesezeichen versehenen Zeile. Wenn `lSkip` ist-1 und die erste Zeile abgerufen wird, die Zeile vor dem Lesezeichen versehenen Zeile.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Bei dieser Methode muss die optionale Schnittstelle `IRowsetLocate`, die möglicherweise nicht auf allen Anbietern unterstützt, wenn dies der Fall ist, gibt die Methode **E_NOINTERFACE**. Müssen Sie auch festlegen **DBPROP_IRowsetLocate** auf `VARIANT_TRUE` und legen Sie **DBPROP_CANFETCHBACKWARDS** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder den Befehl mit dem Rowset zu erstellen.  
  
 Informationen zur Verwendung von Lesezeichen in Consumer finden Sie unter [mithilfe von Lesezeichen](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)