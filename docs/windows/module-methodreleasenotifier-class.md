---
title: 'Module:: methodreleasenotifier-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 204fe04b9c4df566ae50dacbe4981d5b902203d5
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier-Klasse
Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird von einem Objekt und seinem Member Zeiger-zu-Methode angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Objekts, dessen Memberfunktion der Ereignishandler vorhanden ist.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der methodreleasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::Invoke-Methode](../windows/module-methodreleasenotifier-invoke-method.md)|Ruft den Ereignishandler, die dem aktuellen methodreleasenotifier-Objekt zugeordnet.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_-Datenmember](../windows/module-methodreleasenotifier-method-data-member.md)|Enthält einen Zeiger an den Ereignishandler für das aktuelle methodreleasenotifier-Objekt.|  
|[Module::MethodReleaseNotifier::object_-Datenmember](../windows/module-methodreleasenotifier-object-data-member.md)|Enthält einen Zeiger auf das Objekt, dessen Memberfunktion die Ereignishandler für das aktuelle methodreleasenotifier-Objekt ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)