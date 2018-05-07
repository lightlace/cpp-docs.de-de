---
title: 'CRowsetImpl:: Getcommandfromid | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs:
- C++
helpviewer_keywords:
- GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f79e9287bf8d546ba5007257899a6b6ddc27ad40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
Überprüft, wenn eine oder beide Parameter Zeichenfolgenwerte enthält, und wenn dies der Fall ist, kopiert die Zeichenfolgenwerte in der Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTableID`  
 [in] Ein Zeiger auf die **DBID** darstellt, die Tabelle-ID.  
  
 `pIndexID`  
 [in] Ein Zeiger auf die **DBID** darstellt, der die Index-ID  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, über eine statische Upcast von `CRowsetImpl` zum Auffüllen der Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Standardmäßig überprüft diese Methode, um festzustellen, ob eine oder beide Parameter Zeichenfolgenwerte enthalten. Wenn sie Zeichenfolgenwerte enthalten, kopiert diese Methode die Zeichenfolgenwerte auf den Datenmember an. Platziert eine Methode mit der Signatur in Ihrer `CRowsetImpl`-abgeleitete Klasse, die Methode wird anstelle der basisimplementierung aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)