---
title: 'Module:: releasenotifier-Klasse | Microsoft Docs'
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
ms.openlocfilehash: 76edb403fae12dd8b6221d8bd6ec82424bc5a4f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878391"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier-Klasse
Ruft einen Ereignishandler auf, wenn das letzte Objekt in einem Modul freigegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::ReleaseNotifier::~ReleaseNotifier-Destruktor](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der releasenotifier-Klasse.|  
|[Module::ReleaseNotifier::ReleaseNotifier-Konstruktor](../windows/module-releasenotifier-releasenotifier-constructor.md)|Initialisiert eine neue Instanz der releasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::ReleaseNotifier::Invoke-Methode](../windows/module-releasenotifier-invoke-method.md)|Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul veröffentlicht wird.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Löscht das aktuelle releasenotifier-Objekt, wenn das Objekt mit einem Parameter erstellt wurde `true`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)