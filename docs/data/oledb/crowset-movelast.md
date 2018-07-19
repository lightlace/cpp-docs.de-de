---
title: 'CRowset:: MoveLast | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRowset<TAccessor>::MoveLast
- CRowset<TAccessor>::MoveLast
- ATL.CRowset.MoveLast
- ATL::CRowset::MoveLast
- CRowset<TAccessor>.MoveLast
- MoveLast
- CRowset::MoveLast
- ATL.CRowset<TAccessor>.MoveLast
- CRowset.MoveLast
dev_langs:
- C++
helpviewer_keywords:
- MoveLast method
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d02447462393924a446889093c17f1ae0bafde3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096391"
---
# <a name="crowsetmovelast"></a>CRowset::MoveLast
Verschiebt den Cursor auf die letzte Zeile an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveLast() throw();  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe [IRowset:: RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) um den Speicherort des nächsten Abrufvorgang bis zum letzten neu positionieren, und ruft die letzte Zeile ab.  
  
 Diese Methode erfordert, dass Sie festlegen, **DBPROP_CANSCROLLBACKWARDS** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder einen Befehl, der das Rowset enthält. (Sie können auch festlegen, für eine bessere Leistung **DBPROP_QUICKRESTART** auf `VARIANT_TRUE`.)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)