---
title: "CancelTransitionPolicy-Enumeration"
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
  - "module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CancelTransitionPolicy-Enumeration"
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# CancelTransitionPolicy-Enumeration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, wie der Versuch eines asynchronen Vorgangs dem Übergang zu einem Terminalzustand der abgeschlossenen oder Fehler in Bezug auf einen Client\-angeforderten abgebrochenen Zustand verhalten soll.  
  
## Syntax  
  
```  
enum CancelTransitionPolicy;  
```  
  
## Member  
  
### Werte  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`RemainCanceled`|Wenn der asynchrone Vorgang gerade in einem Client\-angeforderten abgebrochenen Zustand ist, bedeutet dies, dass im abgebrochenen Zustand im Gegensatz zu Übergang für einen abgeschlossenen oder Terminal dem Fehlerzustand bleibt.|  
|`TransitionFromCanceled`|Wenn der asynchrone Vorgang gerade in einem Client\-angeforderten abgebrochenen Zustand ist, wird dieser Zustand dass an, Übergang von dem abgebrochener Status zum Terminalzustand der abgeschlossenen oder Fehler auf, wie durch den Aufruf bestimmt, der dieses Flag verwendet.|  
  
## Anforderungen  
 **Header:**  async.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)