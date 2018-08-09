---
title: 'Module:: releasenotifier-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97c998f7e0814c5acae55dd3e9b747faed0242e1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016222"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier-Klasse
Ruft einen Ereignishandler an, wenn das letzte Objekt in einem Modul veröffentlicht wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier-Destruktor](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Hebt die Initialisierung der aktuellen Instanz von der **releasenotifier** Klasse.|  
|[Module::ReleaseNotifier::ReleaseNotifier-Konstruktor](../windows/module-releasenotifier-releasenotifier-constructor.md)|Initialisiert eine neue Instanz der dem **releasenotifier** Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke-Methode](../windows/module-releasenotifier-invoke-method.md)|Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul veröffentlicht wird.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Löscht die aktuelle **releasenotifier** Objekt, wenn das Objekt, mit dem Parameter erstellt wurde **"true"**.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)