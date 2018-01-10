---
title: 'CRowset:: MovePrev | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: MovePrev method
ms.assetid: 7ced2bfb-f556-40fc-97ea-0d4e7213e114
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0dc22504efde2b32311dea998f2ed5d157ea9122
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmoveprev"></a>CRowset::MovePrev
Verschiebt den Cursor auf den vorherigen Datensatz an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT MovePrev( ) throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode erfordert, dass Sie festlegen, **DBPROP_CANFETCHBACKWARDS** oder **DBPROP_CANSCROLLBACKWARDS** auf `VARIANT_TRUE` vor dem Aufruf **öffnen** für die Tabelle oder der Befehl, der das Rowset enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset:: MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset:: MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)