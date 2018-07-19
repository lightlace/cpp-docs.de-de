---
title: 'CRowsetImpl:: ValidateCommandID | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
dev_langs:
- C++
helpviewer_keywords:
- ValidateCommandID method
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b83f0e8bb65a6043a9ca48f87ffe8babfb73e22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098497"
---
# <a name="crowsetimplvalidatecommandid"></a>CRowsetImpl::ValidateCommandID
Überprüfen, ob eine oder beide Ziele überprüft **DBID**s Zeichenfolgenwerte enthalten, und wenn dies der Fall ist, kopiert Sie sie in seinen Datenmembern [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTableID`  
 [in] Ein Zeiger auf die **DBID** , die ID der Tabelle darstellt.  
  
 `pIndexID`  
 [in] Ein Zeiger auf die **DBID** , die Index-ID darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, über eine statische Upcast von `CRowsetImpl` zum Auffüllen von Datenmembern [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Standardmäßig überprüft diese Methode zu überprüfen, ob eine oder beide **DBID**s Zeichenfolgenwerte enthalten, und wenn dies der Fall ist, in seinen Datenmembern kopiert. Platziert eine Methode mit der Signatur in Ihrer `CRowsetImpl`-abgeleitete Klasse, die Methode wird anstelle der basisimplementierung aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)