---
title: 'CBulkRowset:: MoveNext | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBulkRowset<TAccessor>.MoveNext
- ATL::CBulkRowset::MoveNext
- CBulkRowset::MoveNext
- ATL.CBulkRowset.MoveNext
- CBulkRowset.MoveNext
- ATL::CBulkRowset<TAccessor>::MoveNext
- CBulkRowset<TAccessor>.MoveNext
- CBulkRowset<TAccessor>::MoveNext
dev_langs: C++
helpviewer_keywords: MoveNext method
ms.assetid: 788f3344-cf60-4af1-8f5f-0098c8d1a3f0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b08d19387bb30fdf0897b3d36a2769df45302de7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cbulkrowsetmovenext"></a>CBulkRowset::MoveNext
Ruft die nächste Datenzeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT MoveNext( ) throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Gibt zurück, wenn das Ende des Rowsets erreicht wurde, **DB_S_ENDOFROWSET**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)