---
title: "CHandle Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHandle"
  - "ATL::CHandle"
  - "CHandle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHandle class"
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CHandle Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und Verwenden eines Handleobjekts bereit.  
  
## Syntax  
  
```  
  
class CHandle  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHandle::CHandle](../Topic/CHandle::CHandle.md)|Der \-Konstruktor.|  
|[CHandle::~CHandle](../Topic/CHandle::~CHandle.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CHandle::Attach](../Topic/CHandle::Attach.md)|Rufen Sie diese Methode auf, um das Objekt `CHandle` zu einem vorhandenen Handle anzufügen.|  
|[CHandle::Close](../Topic/CHandle::Close.md)|Rufen Sie diese Methode auf, um ein `CHandle`\-Objekt zu schließen.|  
|[CHandle::Detach](../Topic/CHandle::Detach.md)|Rufen Sie diese Methode auf, um ein Handle von einem `CHandle`\-Objekt zu trennen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CHandle::operator HANDLE](../Topic/CHandle::operator%20HANDLE.md)|Gibt den Wert des gespeicherten Handles zurück.|  
|[CHandle::operator \=](../Topic/CHandle::operator%20=.md)|Zuweisungsoperator|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CHandle::m\_h](../Topic/CHandle::m_h.md)|Die Membervariable, die das Handle speichert.|  
  
## Hinweise  
 Ein `CHandle`\-Objekt kann verwendet werden, wenn ein Handle erforderlich ist: der Hauptunterschied liegt darin, dass das Objekt `CHandle` automatisch gelöscht wird.  
  
> [!NOTE]
>  Manche API\-Funktionen verwenden NULL als leeres oder ungültiges Handle, während andere INVALID\_HANDLE\_VALUE verwenden.  Verwendung `CHandle` nur MACHT ungültig und wird INVALID\_HANDLE\_VALUE als echtes Handle behandeln.  Wenn Sie eine API aufrufen, das INVALID\_HANDLE\_VALUE zurückgeben kann, sollten Sie für diesen Wert überprüfen, bevor Sie [CHandle::Attach](../Topic/CHandle::Attach.md) aufrufen oder das `CHandle`\-Konstruktor übergeben, und führen stattdessen NULL.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)