---
title: RoInitializeWrapper-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 41eb5e79ca1471fb8c12ffca420a134115fbfcc1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014038"
---
# <a name="roinitializewrapper-class"></a>RoInitializeWrapper-Klasse
Initialisiert die Windows-Runtime.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class RoInitializeWrapper  
```  
  
## <a name="remarks"></a>Hinweise  
 **RoInitializeWrapper** ist eine Annehmlichkeit, die die Windows-Runtime initialisiert und gibt ein HRESULT zurück, der angibt, ob der Vorgang erfolgreich war. Da der Destruktor einer Klasse aufruft `::Windows::Foundation::Uninitialize`, Instanzen von **RoInitializeWrapper** müssen im globalen oder der obersten Ebene Gültigkeitsbereich deklariert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[RoInitializeWrapper::RoInitializeWrapper-Konstruktor](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Initialisiert eine neue Instanz der dem **RoInitializeWrapper** Klasse.|  
|[RoInitializeWrapper::~RoInitializeWrapper-Destruktor](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Zerstört die aktuelle Instanz von der **RoInitializeWrapper** Klasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[RoInitializeWrapper::HRESULT()-Operator](../windows/roinitializewrapper-hresult-parens-operator.md)|Ruft den HRESULT-Wert, erzeugt die **RoInitializeWrapper** Konstruktor.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `RoInitializeWrapper`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)