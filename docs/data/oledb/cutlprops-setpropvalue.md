---
title: 'CUtlProps:: Setpropvalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cd54b1483d43578bad63afff6eeab74d536ae133
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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