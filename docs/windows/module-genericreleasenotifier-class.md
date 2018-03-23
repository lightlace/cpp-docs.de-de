---
title: 'Module:: genericreleasenotifier-Klasse | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f867b0cff559ead40be9b2e3ff0722fdb9943034
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier-Klasse
Ruft einen Ereignishandler auf, wenn das letzte Objekt im aktuellen Modul freigegeben wird. Der Ereignishandler wird auf ein Lambda, Funktionselement oder Zeiger-auf-Funktion von angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
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