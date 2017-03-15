---
title: "CriticalSection::CriticalSection-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection, Konstruktor"
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::CriticalSection-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert ein Synchronisierungsobjekt, das auf ein Mutex\-Objekt ähnelt, jedoch mit nur die Threads eines einzelnen Prozesses verwendet werden.  
  
## Syntax  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### Parameter  
 `spincount`  
 Die Anzahl der Rotationen zum kritischen Abschnittsobjekt.  Der Standardwert ist 0.  
  
## Hinweise  
 Weitere Informationen über crticial Abschnitte und spincounts, finden Sie die Funktion **InitializeCriticalSectionAndSpinCount** im Synchronisierungsabschnitt des documenation Windows\-API.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Critical\_Section\-Klasse](../windows/criticalsection-class.md)