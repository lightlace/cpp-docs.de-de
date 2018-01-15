---
title: Mutex Class1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex
dev_langs: C++
helpviewer_keywords: Mutex class
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0e849d1fee7eca67f3b5765d31b54e0660eaa25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mutex-class1"></a>Mutex Class1
Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class Mutex : public HandleT<HandleTraits::MutexTraits>  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|**SyncLock**|Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.|  
  
### <a name="public-constructor"></a>Öffentlicher Konstruktor  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Mutex::Mutex-Konstruktor](../windows/mutex-mutex-constructor.md)|Initialisiert eine neue Instanz der Mutex-Klasse.|  
  
### <a name="public-members"></a>Öffentliche Member  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Mutex::Lock-Methode](../windows/mutex-lock-method.md)|Wartet, bis das aktuelle Objekt oder die Mutex-Objekt, das dem angegebenen Handle zugeordnete frei Mutex oder das angegebene Timeoutintervall abgelaufen.|  
  
### <a name="public-operator"></a>Öffentlicher Operator  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Mutex::operator=-Operator](../windows/mutex-operator-assign-operator.md)|Weist (wechselt) der angegebene Mutex-Objekt in der aktuellen Mutex-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Mutex`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)