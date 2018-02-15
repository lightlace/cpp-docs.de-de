---
title: 'CUtlProps:: GetPropValue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
dev_langs:
- C++
helpviewer_keywords:
- GetPropValue method
ms.assetid: 9a3fbadb-7814-48f7-96a4-b960fc4ecf2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c4e9ea040c9ec458f100beb4c9cd2516ac167052
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cutlpropsgetpropvalue"></a>CUtlProps::GetPropValue
Ruft eine Eigenschaft aus einer Eigenschaft ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pguidPropSet`  
 [in] Die GUID für den Eigenschaftensatz.  
  
 `dwPropId`  
 [in] Der Property-Index.  
  
 `pvValue`  
 [out] Ein Zeiger auf einen Variant-Wert, der den neue Eigenschaftswert enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `Failure` Bei einem Fehler und `S_OK` bei Erfolg.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CUtlProps-Klasse](../../data/oledb/cutlprops-class.md)