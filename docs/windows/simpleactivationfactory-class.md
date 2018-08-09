---
title: SimpleActivationFactory-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97ad430bc0ab5a268ff428189da5987b6c45907d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650790"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory-Klasse
Stellt einen grundlegenden Mechanismus für das Erstellen einer Windows-Runtime oder einer klassischen COM-Basisklasse bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
### <a name="parameters"></a>Parameter  
 *Basis*  
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
|[SimpleActivationFactory::GetRuntimeClassName-Methode](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Ruft den Common Language Runtime-Klassennamen einer Instanz der Klasse gemäß den *Base* Klassenvorlagenparameter.|  
|[SimpleActivationFactory::GetTrustLevel-Methode](../windows/simpleactivationfactory-gettrustlevel-method.md)|Ruft die Vertrauensebene der eine Instanz der Klasse, die gemäß der *Base* Klassenvorlagenparameter.|  
  
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