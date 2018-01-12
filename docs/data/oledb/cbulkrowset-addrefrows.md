---
title: 'CBulkRowset:: Addrefrows | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset::AddRefRows
- AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
dev_langs: C++
helpviewer_keywords: AddRefRows method
ms.assetid: 014be991-50f8-4377-ba16-fec80b54b406
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43227ac0bddce6ac078364ff5ea1650616f8db53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetaddrefrows"></a>CBulkRowset::AddRefRows
Aufrufe [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) inkrementiert den Verweiszähler für alle Zeilen, die derzeit von der Bulk-Rowset abgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)