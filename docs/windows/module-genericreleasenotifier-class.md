---
title: 'Module:: genericreleasenotifier-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs: C++
helpviewer_keywords: GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c87205d1d52c8273ac7eea55fcc5385810349f1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier-Klasse
Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird auf ein Lambda, Funktionselement oder Zeiger-auf-Funktion von angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Datenmembers, der den Speicherort des ereignishandlers enthält.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der genericreleasenotifier-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke-Methode](../windows/module-genericreleasenotifier-invoke-method.md)|Ruft den Ereignishandler, die dem aktuellen genericreleasenotifier-Objekt zugeordnet.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_-Datenmember](../windows/module-genericreleasenotifier-callback-data-member.md)|Enthält den Lambda, Funktionselement oder Zeiger auf Funktion Ereignishandler, die dem aktuellen genericreleasenotifier-Objekt zugeordnet.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [Module-Klasse](../windows/module-class.md)