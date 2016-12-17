---
title: "Critical_Section-Klasse"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection-Klasse"
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Critical_Section-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einem kritischen Abschnittsobjekt dar.  
  
## Syntax  
  
```  
class CriticalSection;  
```  
  
## Member  
  
### Konstruktor  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CriticalSection::CriticalSection\-Konstruktor](../windows/criticalsection-criticalsection-constructor.md)|Initialisiert ein Synchronisierungsobjekt, das auf ein Mutex\-Objekt ähnelt, jedoch mit nur die Threads eines einzelnen Prozesses verwendet werden.|  
|[CriticalSection::~CriticalSection\-Destruktor](../windows/criticalsection-tilde-criticalsection-destructor.md)|Deinitialisiert und zerstört das aktuelle CriticalSections\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CriticalSection::TryLock\-Methode](../windows/criticalsection-trylock-method.md)|Versucht, einen kritischen Abschnitt einzugeben, ohne zu blockieren.  Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread Besitz des kritischen Abschnitts.|  
|[CriticalSection::Lock\-Methode](../windows/criticalsection-lock-method.md)|Wartet Besitzer des angegebenen Abschnittsobjekts kritischen.  Die Funktion wird zurückgegeben, wenn der aufrufende Thread Besitz gewährt wird.|  
|[CriticalSection::IsValid\-Methode](../windows/criticalsection-isvalid-method.md)|Gibt an, ob der aktuelle kritischen Abschnitt gültig ist.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[CriticalSection::cs\_\-Datenmember](../windows/criticalsection-cs-data-member.md)|Deklariert einen Datenmember des kritischen Abschnitts.|  
  
## Vererbungshierarchie  
 `CriticalSection`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)