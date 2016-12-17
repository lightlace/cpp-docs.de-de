---
title: "CriticalSection::Lock-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lock-Methode"
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# CriticalSection::Lock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wartet Besitzer des angegebenen Abschnittsobjekts kritischen.  Die Funktion wird zurückgegeben, wenn der aufrufende Thread Besitz gewährt wird.  
  
## Syntax  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Parameter  
 `cs`  
 Ein vom Benutzer angegebenes kritisches Abschnittsobjekt.  
  
## Rückgabewert  
 Ein Sperrenobjekt, das verwendet werden kann, um den aktuellen kritischen Abschnitt zu entsperren.  
  
## Hinweise  
 Die erste Funktion **Lock** beeinflusst das aktuelle kritischen Abschnittsobjekt.  Die zweite **Lock**\-Funktion betrifft einen vom Benutzer angegebenen kritischen Abschnitt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Critical\_Section\-Klasse](../windows/criticalsection-class.md)