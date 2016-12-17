---
title: "Compilerwarnung (Stufe 1) C4391"
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
  - "C4391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4391"
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Signatur': Falscher Rückgabetyp für systeminterne Funktion. Erwartet: 'Typ'  
  
 Eine Funktionsdeklaration für eine systeminterne Compilerfunktion hatte den falschen Rückgabetyp.  Die resultierende Anwendung wird möglicherweise nicht einwandfrei ausgeführt.  
  
 Um diese Warnung zu vermeiden, korrigieren Sie entweder die Deklaration oder löschen sie und führen einfach \#include für die entsprechende Headerdatei aus.  
  
 Im folgenden Beispiel wird C4391 generiert:  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```