---
title: 'Activationfactory:: Gettrustlevel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4bddc5a453e1c3aac43fe58d105ccef863c67808
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652268"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel-Methode
Ruft der Vertrauensebene des Objekts ab, das aktuelle **ActivationFactory** instanziiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
### <a name="parameters"></a>Parameter  
 *trustLvl*  
 Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene der Runtime-Klasse, die **ActivationFactory** instanziiert.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Andernfalls wird ein Assertionsfehler ausgegeben und *TrustLvl* nastaven NA hodnotu `FullTrust`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ActivationFactory-Klasse](../windows/activationfactory-class.md)