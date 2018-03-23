---
title: SimpleActivationFactory-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f6aabaae1e19fef3631e372391c81108f212c90
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory-Klasse
Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Eine Basisklasse.  
  
## <a name="remarks"></a>Hinweise  
 Die Basisklasse muss einen Standardkonstruktor bereitstellen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie mit SimpleActivationFactory mit der [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) Makro.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SimpleActivationFactory::ActivateInstance-Methode](../windows/simpleactivationfactory-activateinstance-method.md)|Erstellt eine Instanz der angegebenen Schnittstelle.|  
|[SimpleActivationFactory::GetRuntimeClassName-Methode](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Ruft die Laufzeitklasse-Namen, der eine Instanz der Klasse, die gemäß der `Base` Klassenvorlagenparameter.|  
|[SimpleActivationFactory::GetTrustLevel-Methode](../windows/simpleactivationfactory-gettrustlevel-method.md)|Ruft die Vertrauensebene einer Instanz der Klasse, die gemäß der `Base` Klassenvorlagenparameter.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)