---
title: RoInitializeWrapper-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 05/20/2018
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
ms.openlocfilehash: cac71857e6b472f11d1c9eaba48d181ea78fb456
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705591"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper-Klasse
Initialisiert die Windows-Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Hinweise  
 RoInitializeWrapper ist eine benutzerfreundliche, die Windows-Runtime initialisiert und gibt ein HRESULT zurück, der angibt, ob der Vorgang erfolgreich war. Da der Destruktor der Klasse aufruft `::Windows::Foundation::Uninitialize`, Instanzen von `RoInitializeWrapper` müssen global oder auf der obersten Ebene Gültigkeitsbereich deklariert werden.  
  
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