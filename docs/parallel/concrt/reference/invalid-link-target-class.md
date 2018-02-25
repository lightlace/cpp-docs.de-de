---
title: Invalid_link_target-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
dev_langs:
- C++
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3a4ac6888f22fcedb494865a219fc0dd8e8a98c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="invalidlinktarget-class"></a>invalid_link_target-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `link_target`-Methode eines Meldungsblocks aufgerufen wird und der Meldungsblock keine Verknüpfung mit dem Ziel erstellen kann. Dies kann das Ergebnis vom Überschreiten der Anzahl zulässiger Links für den Meldungsblock sein oder das Ergebnis von Versuchen, ein bestimmtes Ziel zweimal mit der gleichen Quelle zu verknüpfen.  
  
## <a name="syntax"></a>Syntax  
  
```
class invalid_link_target : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[invalid_link_target](#ctor)|Überladen. Erstellt ein `invalid_link_target`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_link_target`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> invalid_link_target 

 Erstellt ein `invalid_link_target`-Objekt.  
  
```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)



