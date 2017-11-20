---
title: 'CBulkRowset:: setRows | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs: C++
helpviewer_keywords: SetRows method
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 543ea1fcc1a87319e9a9ca952417f76f140663f6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cbulkrowsetsetrows"></a>CBulkRowset::SetRows
Legt die Anzahl von Zeilenhandles, die von jedem Aufruf abgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void SetRows(  
   DBROWCOUNT nRows   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nRows`  
 [in] Die neue Größe des Rowsets (Anzahl von Zeilen).  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion aufrufen, muss es sein, bevor das Rowset geöffnet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)