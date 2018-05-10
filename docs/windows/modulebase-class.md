---
title: ModuleBase-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bfee0c0cd7ff7bd7f4525a291184f08f1e2898e5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="modulebase-class"></a>ModuleBase-Klasse
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Hinweise  
 Stellt die Basisklasse der [Modul](../windows/module-class.md) Klassen.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ModuleBase::ModuleBase-Konstruktor](../windows/modulebase-modulebase-constructor.md)|Initialisiert eine Instanz der Module-Klasse.|  
|[ModuleBase::~ModuleBase-Destruktor](../windows/modulebase-tilde-modulebase-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der Module-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount-Methode](../windows/modulebase-decrementobjectcount-method.md)|Bei der Implementierung nachverfolgt verringert die Anzahl der Objekte vom Modul an.|  
|[ModuleBase::IncrementObjectCount-Methode](../windows/modulebase-incrementobjectcount-method.md)|Bei der Implementierung erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ModuleBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)