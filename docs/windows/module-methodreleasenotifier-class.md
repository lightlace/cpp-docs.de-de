---
title: "Module::MethodReleaseNotifier-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier-Klasse"
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::MethodReleaseNotifier-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird durch ein Objekt und seine Member Zeiger-zu-Methode angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Objekts, dessen Memberfunktion der Ereignishandler ist.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der methodreleasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module:: methodreleasenotifier:: Invoke-Methode](../windows/module-methodreleasenotifier-invoke-method.md)|Ruft den Ereignishandler mit dem aktuellen methodreleasenotifier-Objekt verknüpft ist.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::MethodReleaseNotifier::method_-Datenmember](../windows/module-methodreleasenotifier-method-data-member.md)|Enthält einen Zeiger an den Ereignishandler für das aktuelle methodreleasenotifier-Objekt.|  
|[Module::MethodReleaseNotifier::object_-Datenmember](../windows/module-methodreleasenotifier-object-data-member.md)|Enthält einen Zeiger auf das Objekt, dessen Memberfunktion der Ereignishandler für das aktuelle methodreleasenotifier-Objekt ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)