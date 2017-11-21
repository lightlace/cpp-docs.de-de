---
title: Semaphore-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Semaphore
dev_langs: C++
helpviewer_keywords: Semaphore class
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 10de04ebed31835d93daca9cf4caa5d96ed605b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="semaphore-class"></a>Semaphore-Klasse
Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`SyncLock`|Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::Semaphore-Konstruktor](../windows/semaphore-semaphore-constructor.md)|Initialisiert eine neue Instanz der Semaphore-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[InvokeHelper::Invoke-Methode](../windows/invokehelper-invoke-method.md)|Ruft den Ereignishandler, dessen Signatur mit der angegebene Anzahl von Argumenten enthält.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::Lock-Methode](../windows/semaphore-lock-method.md)|Wartet, bis das aktuelle Objekt oder das Objekt, das dem angegebenen Handle zugeordnet ist, in dem Zustand "signalisiert" oder das angegebene Timeoutintervall abgelaufen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Semaphore::operator=-Operator](../windows/semaphore-operator-assign-operator.md)|Verschiebt das angegebene Handle aus einem Semaphorobjekt mit dem aktuellen Semaphore-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Semaphore`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Wrappers-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)