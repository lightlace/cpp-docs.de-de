---
title: "Verwenden von &quot;atexit&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit-Funktion"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von &quot;atexit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der Funktion [atexit](../c-runtime-library/reference/atexit.md) können Sie eine Funktion zur Beendigung der Verarbeitung angeben, die vor der Beendigung des Programms ausgeführt wird.  Es werden keine globalen statischen Objekte, die vor dem Aufruf von `atexit` initialisiert werden, vor Ausführung der Funktion zur Beendigung der Verarbeitung zerstört.  
  
## Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)