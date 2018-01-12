---
title: 'Csimplerow:: Compare | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 87ee21022aa379820ced0463892be12ee0676d88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRow`  
 Ein Zeiger auf eine `CSimpleRow` Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein `HRESULT` Wert, normalerweise `S_OK`, der angibt, die zwei Zeilen sind die gleiche Zeileninstanz oder **"S_FALSE"**, unterscheiden, der angibt, der zwei Zeilen. Finden Sie unter [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in der *OLE DB Programmer's Reference* für andere mögliche Rückgabewerte.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleRow-Klasse](../../data/oledb/csimplerow-class.md)   
 [Csimplerow:: Releaserow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)