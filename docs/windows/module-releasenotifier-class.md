---
title: "Module::ReleaseNotifier-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier-Klasse"
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::ReleaseNotifier-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt in einem Modul freigegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class ReleaseNotifier;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Releasenotifier:: ~ ReleaseNotifier-Destruktor](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|Hebt die Initialisierung der aktuellen Instanz der releasenotifier-Klasse.|  
|[Module::ReleaseNotifier::ReleaseNotifier-Konstruktor](../windows/module-releasenotifier-releasenotifier-constructor.md)|Initialisiert eine neue Instanz der releasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Releasenotifier:: Invoke-Methode](../windows/module-releasenotifier-invoke-method.md)|Ruft bei Implementierung einen Ereignishandler aus, wenn das letzte Objekt in einem Modul freigegeben wird.|  
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|Löscht das aktuelle releasenotifier-Objekt, wenn das Objekt, mit dem Parameter erstellt wurde `true`.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)