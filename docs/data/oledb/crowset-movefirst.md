---
title: 'CRowset:: MoveFirst | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::MoveFirst
- ATL::CRowset::MoveFirst
- CRowset<TAccessor>.MoveFirst
- CRowset::MoveFirst
- CRowset.MoveFirst
- ATL.CRowset.MoveFirst
- ATL.CRowset<TAccessor>.MoveFirst
- ATL::CRowset<TAccessor>::MoveFirst
dev_langs:
- C++
helpviewer_keywords:
- MoveFirst method
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c7937562c0e59dec466565f549ee9c9400175f9a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetmovefirst"></a>CRowset::MoveFirst
Verschiebt den Cursor in der ersten Position aus, und ruft die erste Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT MoveFirst() throw();  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe [IRowset:: RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) , positionieren den weiter-Fetch-Speicherort, an die Anfangsposition (die Position, die den weiter-Fetch-Speicherort wurde, wenn das Rowset erstellt wurde) und ruft die erste Zeile ab.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)