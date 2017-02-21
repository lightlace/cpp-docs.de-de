---
title: "Compilerwarnung (Stufe 1) C4391 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4391"
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
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