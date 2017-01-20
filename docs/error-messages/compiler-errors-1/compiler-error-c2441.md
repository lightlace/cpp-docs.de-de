---
title: "Compilerfehler C2441"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2441"
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Variable': Ein mit \_\_declspec\(process\) deklariertes Symbol muss im \/clr:pure\-Modus konstant sein  
  
 In der Standardeinstellung sind Variablen unter **\/clr:pure** anwendungsdomänenspezifisch.  Eine mit `__declspec(process)` gekennzeichnete Variable unter **\/clr:pure** ist fehleranfällig, wenn diese in einer Anwendungsdomäne geändert und in einer anderen gelesen wird.  
  
 Daher wird vom Compiler erzwungen, dass prozessspezifische Variablen unter **\/clr:pure** vom Typ `const` und in allen Anwendungsdomänen schreibgeschützt sind.  
  
 Weitere Informationen finden Sie unter [Prozess](../../cpp/process.md) und [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2441 generiert.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```