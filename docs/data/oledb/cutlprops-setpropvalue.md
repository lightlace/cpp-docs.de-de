---
title: 'CUtlProps:: Setpropvalue | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 73f2432a23adf8fe11f759c2caa85d9653040635
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099068"
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