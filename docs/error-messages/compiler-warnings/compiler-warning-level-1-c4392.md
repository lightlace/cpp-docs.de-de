---
title: "Compilerwarnung (Stufe 1) C4392 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4392"
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Signatur': Falsche Anzahl von Argumenten für systeminterne Funktion. 'Anzahl' Argumente erwartet  
  
 Eine Funktionsdeklaration für eine systeminterne Compilerfunktion hatte die falsche Anzahl von Argumenten.  Die resultierende Anwendung wird möglicherweise nicht einwandfrei ausgeführt.  
  
 Um diese Warnung zu vermeiden, korrigieren Sie entweder die Deklaration oder löschen sie und führen einfach \#include für die entsprechende Headerdatei aus.  
  
 Im folgenden Beispiel wird C4392 generiert:  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```