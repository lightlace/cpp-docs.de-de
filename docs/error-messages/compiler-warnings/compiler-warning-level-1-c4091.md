---
title: "Compilerwarnung (Stufe 1) C4091"
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
  - "C4091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4091"
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort': Ignoriert auf der linken Seite von 'Typ', wenn keine Variable deklariert wurde  
  
 Der Compiler hat eine Situation erkannt, in der der Benutzer wahrscheinlich eine Variable deklarieren wollte, die der Compiler jedoch nicht deklarieren konnte.  
  
## Beispiel  
 Ein `__declspec`\-Attribut am Anfang einer benutzerdefinierten Typdeklaration wird auf die Variable dieses Typs angewendet.  Warnung C4091 weist darauf hin, dass keine Variable deklariert wurde.  Im folgenden Beispiel wird C4091 generiert.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## Beispiel  
 Wenn es sich bei einem Bezeichner um eine Typdefinition handelt, kann dieser nicht gleichzeitig ein Variablenname sein.  Im folgenden Beispiel wird C4091 generiert.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```