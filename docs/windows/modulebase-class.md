---
title: ModuleBase-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b02efe3ee61234b2439c1cbbae07827d6a879b2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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