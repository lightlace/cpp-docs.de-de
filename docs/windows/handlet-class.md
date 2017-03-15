---
title: "HandleT-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT-Klasse"
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HandleT-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Handle für ein Objekt dar.  
  
## Syntax  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### Parameter  
 `HandleTraits`  
 Eine Instanz der [HandleTraits](../windows/handletraits-structure.md) die allgemeine Struktur, Eigenschaften eines Handles definiert.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Traits`|Ein Synonym für `HandleTraits`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HandleT::HandleT\-Konstruktor](../windows/handlet-handlet-constructor.md)|Initialisiert eine neue Instanz der HandleT\-Klasse.|  
|[HandleT::~HandleT\-Destruktor](../windows/handlet-tilde-handlet-destructor.md)|Deinitialisiert eine Instanz der HandleT\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HandleT::Attach\-Methode](../windows/handlet-attach-method.md)|Ordnet das angegebene Handle mit dem aktuellen HandleT\-Objekt zu.|  
|[HandleT::Close\-Methode](../windows/handlet-close-method.md)|Schließt das aktuelle HandleT\-Objekt.|  
|[HandleT::Detach\-Methode](../windows/handlet-detach-method.md)|Hebt des aktuellen HandleT\-Objekts von seinem zugrunde liegenden Handle die Zuordnung.|  
|[HandleT::Get\-Methode](../windows/handlet-get-method.md)|Ruft den Wert des zugrunde liegenden Handles ab.|  
|[HandleT::IsValid\-Methode](../windows/handlet-isvalid-method.md)|Gibt an, ob das aktuelle HandleT\-Objekt ein Handle darstellt.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HandleT::InternalClose\-Methode](../windows/handlet-internalclose-method.md)|Schließt das aktuelle HandleT\-Objekt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HandleT::operator\=\-Operator](../windows/handlet-operator-assign-operator.md)|Verschiebt den Wert des angegebenen HandleT\-Objekts dem aktuellen HandleT\-Objekt.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HandleT::handle\_ Data\-Member](../windows/handlet-handle-data-member.md)|Enthält das Handle, das vom HandleT\-Objekt dargestellt wird.|  
  
## Vererbungshierarchie  
 `HandleT`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)