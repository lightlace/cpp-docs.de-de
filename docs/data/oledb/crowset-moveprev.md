---
title: 'CRowset:: MovePrev | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>.MovePrev
- CRowset.MovePrev
- MovePrev
- CRowset::MovePrev
- ATL.CRowset.MovePrev
- ATL::CRowset<TAccessor>::MovePrev
- ATL::CRowset::MovePrev
- ATL.CRowset<TAccessor>.MovePrev
- CRowset<TAccessor>::MovePrev
dev_langs:
- C++
helpviewer_keywords:
- MovePrev method
ms.assetid: 7ced2bfb-f556-40fc-97ea-0d4e7213e114
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b86a5266faefaacb0df940f51985f1d31dd006b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetmoveprev"></a>CRowset::MovePrev
Verschiebt den Cursor auf den vorherigen Datensatz an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MovePrev() throw();  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erfordert, dass Sie festlegen, **DBPROP_CANFETCHBACKWARDS** oder **DBPROP_CANSCROLLBACKWARDS** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder der Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)