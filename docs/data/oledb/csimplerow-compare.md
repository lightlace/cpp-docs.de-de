---
title: 'Csimplerow:: Compare | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d79e753f1f4af630c26ef07fbb7241576535ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098964"
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Vergleicht zwei Zeilen, um festzustellen, ob sie auf die gleiche Zeileninstanz verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
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
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)