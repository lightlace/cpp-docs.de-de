---
title: "CriticalSection::TryLock-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryLock-Methode"
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::TryLock-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Versucht, einen kritischen Abschnitt einzugeben, ohne zu blockieren.  Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread Besitz des kritischen Abschnitts.  
  
## Syntax  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Parameter  
 `cs`  
 Ein vom Benutzer angegebenes kritisches Abschnittsobjekt.  
  
## Rückgabewert  
 Ein Wert ungleich 0 \(null\), wenn ein kritischer Abschnitt erfolgreich eingegeben wird oder der aktuelle Thread besitzt bereits den kritischen Abschnitt.  Null wenn ein anderer Thread bereits den kritischen Abschnitt besitzt.  
  
## Hinweise  
 Die erste Funktion **TryLock** beeinflusst das aktuelle kritischen Abschnittsobjekt.  Die zweite **TryLock**\-Funktion betrifft einen vom Benutzer angegebenen kritischen Abschnitt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Critical\_Section\-Klasse](../windows/criticalsection-class.md)