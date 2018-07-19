---
title: 'CBulkRowset:: MoveToBookmark | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b1911fe170262e65ef06e65649f837a0b723d05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094646"
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Dadurch wird die Zeile markiert ein Lesezeichen bzw. die Zeile mit einem angegebenen Offset (`lSkip`) von diesem Lesezeichen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `bookmark`  
 [in] Ein Lesezeichen, markieren den Speicherort, aus dem Daten abgerufen werden sollen.  
  
 `lSkip`  
 [in] Die Anzahl Anzahl von Zeilen aus das Lesezeichen Zielzeile. Wenn `lSkip` NULL ist, wird die erste Zeile abgerufen wird, dem Lesezeichen versehenen Zeile. Wenn `lSkip` 1, ist die erste Zeile abgerufen wird die Zeile nach dem Lesezeichen versehenen Zeile. Wenn `lSkip` ist-1 und die erste Zeile abgerufen wird, die Zeile vor dem Lesezeichen versehenen Zeile.  
  
## <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IRowset:: GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)