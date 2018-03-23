---
title: SimpleClassFactory-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b6cdca5ecf84a9c0c21d37fcaef281df7665cacc
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory-Klasse
Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Base`  
 Eine Basisklasse.  
  
## <a name="remarks"></a>Hinweise  
 Die Basisklasse muss einen Standardkonstruktor bereitstellen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie mit SimpleClassFactory mit der [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) Makro.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[SimpleClassFactory::CreateInstance-Methode](../windows/simpleclassfactory-createinstance-method.md)|Erstellt eine Instanz der angegebenen Schnittstelle.|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)