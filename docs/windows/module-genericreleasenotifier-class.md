---
title: "Module::GenericReleaseNotifier-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier-Klasse"
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Module::GenericReleaseNotifier-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird einen Ereignishandler aufgerufen, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird durch ein Lambda, ein Funktionselement oder Zeiger auf Funktion angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Datenelements, den Speicherort für den Ereignishandler enthält.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der genericreleasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module:: genericreleasenotifier:: Invoke-Methode](../windows/module-genericreleasenotifier-invoke-method.md)|Ruft den Ereignishandler mit dem aktuellen genericreleasenotifier-Objekt verknüpft ist.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_-Datenmember](../windows/module-genericreleasenotifier-callback-data-member.md)|Enthält den Lambda-, Funktionselement oder Zeiger auf Funktion Ereignishandler, die das aktuelle genericreleasenotifier-Objekt zugeordnet.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)