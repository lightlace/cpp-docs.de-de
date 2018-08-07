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
ms.openlocfilehash: 1deeb3076d3f1bfc2243ec333f258f543a37fceb
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608390"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier-Klasse
Ruft einen Ereignishandler an, wenn das letzte Objekt in einem Modul veröffentlicht wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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