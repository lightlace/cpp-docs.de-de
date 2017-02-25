---
title: "Verwenden von &quot;atexit&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "atexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "atexit-Funktion"
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Verwenden von &quot;atexit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der Funktion [atexit](../c-runtime-library/reference/atexit.md) können Sie eine Funktion zur Beendigung der Verarbeitung angeben, die vor der Beendigung des Programms ausgeführt wird.  Es werden keine globalen statischen Objekte, die vor dem Aufruf von `atexit` initialisiert werden, vor Ausführung der Funktion zur Beendigung der Verarbeitung zerstört.  
  
## Siehe auch  
 [Weitere Überlegungen zur Beendigung](../cpp/additional-termination-considerations.md)