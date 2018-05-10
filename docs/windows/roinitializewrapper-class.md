---
title: RoInitializeWrapper-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4a4479686d3ca591a9fdd1c0659549a2e0db6e1c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper-Klasse
Initialisiert die Windows-Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Hinweise  
 RoInitializeWrapper ist eine benutzerfreundliche, die Windows-Runtime initialisiert und gibt ein HRESULT zurück, der angibt, ob der Vorgang erfolgreich war.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper-Konstruktor](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Initialisiert eine neue Instanz der RoInitializeWrapper-Klasse.|  
|[RoInitializeWrapper::~RoInitializeWrapper-Destruktor](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Zerstört die aktuelle Instanz der RoInitializeWrapper-Klasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT()-Operator](../windows/roinitializewrapper-hresult-parens-operator.md)|Ruft das HRESULT, das vom RoInitializeWrapper-Konstruktor erzeugt wird.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)