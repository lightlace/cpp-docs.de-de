---
title: 'Simpleactivationfactory:: Gettrustlevel-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b08ce574a8370eb0029a702f8fa4a4b12c6e93c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892617"
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>SimpleActivationFactory::GetTrustLevel-Methode
Ruft die Vertrauensebene einer Instanz der Klasse, die gemäß der `Base` Klassenvorlagenparameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Parameter  
 `trustLvl`  
 Wenn dieser Vorgang abgeschlossen wird, die Vertrauensebene des aktuellen Klassenobjekts.  
  
## <a name="return-value"></a>Rückgabewert  
 Stets S_OK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)