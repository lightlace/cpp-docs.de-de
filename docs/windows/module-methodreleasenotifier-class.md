---
title: 'Module:: methodreleasenotifier-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b2653128415cfd847db5b9592df116ffd0d470
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014311"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier-Klasse
Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler wird von einem Objekt und seine Member Zeiger-zu-Methode angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ des Objekts, dessen Memberfunktion der Ereignishandler ist.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der dem **methodreleasenotifier** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke-Methode](../windows/module-methodreleasenotifier-invoke-method.md)|Ruft den Ereignishandler verknüpft ist, mit dem aktuellen **methodreleasenotifier** Objekt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_-Datenmember](../windows/module-methodreleasenotifier-method-data-member.md)|Enthält einen Zeiger auf den Ereignishandler für das aktuelle **methodreleasenotifier** Objekt.|  
|[Module::MethodReleaseNotifier::object_-Datenmember](../windows/module-methodreleasenotifier-object-data-member.md)|Enthält einen Zeiger auf das Objekt, dessen Memberfunktion der Ereignishandler für das aktuelle ist **methodreleasenotifier** Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)