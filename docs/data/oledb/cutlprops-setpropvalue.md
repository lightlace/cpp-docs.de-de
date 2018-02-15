---
title: 'CUtlProps:: Setpropvalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs:
- C++
helpviewer_keywords:
- SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f129453d438858b4a4f74c8fc6bf602c97e33e56
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Festlegen einer Eigenschaft in einem Eigenschaftensatz.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pguidPropSet`  
 [in] Die GUID für den Eigenschaftensatz.  
  
 `dwPropId`  
 [in] Der Property-Index.  
  
 `pvValue`  
 [in] Ein Zeiger auf einen Variant-Wert, der den neue Eigenschaftswert enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 `Failure` Bei einem Fehler und `S_OK` bei Erfolg.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CUtlProps-Klasse](../../data/oledb/cutlprops-class.md)