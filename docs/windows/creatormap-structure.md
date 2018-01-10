---
title: CreatorMap-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs: C++
helpviewer_keywords: CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a941f052527b3617772bcb18b2092fdc35ea3a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creatormap-structure"></a>CreatorMap-Struktur
Unterstützt die Windows Runtime C++ Template Library-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>Hinweise  
 Enthält Informationen zum Initialisieren, registrieren und Aufheben der Registrierung Objekten.  
  
 CreatorMap enthält die folgenden Informationen an:  
  
-   Wie zu initialisieren, registrieren und Aufheben der Registrierung Objekten.  
  
-   Wie Aktivierungsdaten je nach einer klassischen COM oder Windows-Runtime-Factory verglichen.  
  
-   Informationen über die Factory Cache und den Servernamen für eine Schnittstelle.  
  
## <a name="members"></a>Member  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CreatorMap::activationId-Datenmember](../windows/creatormap-activationid-data-member.md)|Stellt eine Objekt-ID, die entweder durch eine klassische COM-Klassen-ID oder einen Namen für die Windows-Runtime identifiziert wird.|  
|[CreatorMap::factoryCache-Datenmember](../windows/creatormap-factorycache-data-member.md)|Den Zeiger auf den kanalfactorycache für die CreatorMap gespeichert.|  
|[CreatorMap::factoryCreator-Datenmember](../windows/creatormap-factorycreator-data-member.md)|Erstellt eine Factory für die angegebene CreatorMap an.|  
|[CreatorMap::serverName-Datenmember](../windows/creatormap-servername-data-member.md)|Speichert den Servernamen für die CreatorMap an.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CreatorMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)