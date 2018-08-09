---
title: 'Simpleactivationfactory:: Gettrustlevel-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 22fa30a3662897b171245da194573ec17da2f64e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645187"
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>SimpleActivationFactory::GetTrustLevel-Methode
Ruft die Vertrauensebene der eine Instanz der Klasse, die gemäß der `Base` Klassenvorlagenparameter.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
### <a name="parameters"></a>Parameter  
 *trustLvl*  
 Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene des aktuellen Klassenobjekts.  
  
## <a name="return-value"></a>Rückgabewert  
 Stets S_OK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)