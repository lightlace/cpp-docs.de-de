---
title: "MakeAllocator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MakeAllocator-Klasse"
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MakeAllocator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,   
   T)> , T)> class MakeAllocator;  
  
template<  
   typename T  
>  
class MakeAllocator<T, false>;  
  
template<  
   typename T  
>  
class MakeAllocator<T, true>;  
```  
  
#### Parameter  
 `T`  
 Ein Typname.  
  
 `hasWeakReferenceSupport`  
 `true`, zum Speicher für ein Objekt zu belegen, das schwache Verweise unterstützt; `false`, zum Speicher für ein Objekt zu belegen, das schwache Verweise nicht unterstützt.  
  
## Hinweise  
 Belegt aktivierbare für eine Klasse, mit oder ohne Bezugsunterstützung schwache Speicher.  
  
 Überschreiben Sie die MakeAllocator\-Klasse, um ein benutzerdefiniertes Speicherbelegungsmodell zu implementieren.  
  
 MakeAllocator wird normalerweise verwendet, um Speicherverluste zu verhindern, wenn ein Objekt während der Konstruktion ausgelöst wird.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[MakeAllocator::MakeAllocator\-Konstruktor](../windows/makeallocator-makeallocator-constructor.md)|Initialisiert eine neue Instanz der MakeAllocator\-Klasse.|  
|[MakeAllocator::~MakeAllocator\-Destruktor](../windows/makeallocator-tilde-makeallocator-destructor.md)|Deinitialisiert die aktuelle Instanz der MakeAllocator\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[MakeAllocator::Allocate\-Methode](../windows/makeallocator-allocate-method.md)|Belegt Speicher und ordnet ihn dem aktuellen MakeAllocator\-Objekt zu.|  
|[MakeAllocator::Detach\-Methode](../windows/makeallocator-detach-method.md)|Hebt des Arbeitsspeichers die Zuordnung durch die [Zuordnen zu](../windows/makeallocator-allocate-method.md)\-Methode vom aktuellen MakeAllocator\-Objekt zugeordnet ist.|  
  
## Vererbungshierarchie  
 `MakeAllocator`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)