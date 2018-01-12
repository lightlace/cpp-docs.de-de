---
title: 'CRowsetImpl:: Getcommandfromid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
dev_langs: C++
helpviewer_keywords: GetCommandFromID method
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e75fbd00b6ee2e4a19cf0fe39d0bcda9f0314f8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetimplgetcommandfromid"></a>CRowsetImpl::GetCommandFromID
Überprüft, wenn eine oder beide Parameter Zeichenfolgenwerte enthält, und wenn dies der Fall ist, kopiert die Zeichenfolgenwerte in der Datenmember [M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
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