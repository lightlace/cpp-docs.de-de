---
title: "Compilerwarnung (Stufe 1) C4286"
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
  - "C4286"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4286"
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4286
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ1': wurde aufgefangen durch Basisklasse \('Typ2'\) in Zeilennummer  
  
 Der angegebene Ausnahmetyp wird von einem vorherigen Handler verarbeitet.  Der Typ für den zweiten **catch**\-Vorgang wird vom Typ des ersten Vorgangs abgeleitet.  Ausnahmen für eine Basisklasse fangen Ausnahmen für eine abgeleitete Klasse auf.  
  
## Beispiel  
  
```  
//C4286.cpp  
// compile with: /W1  
#include <eh.h>  
class C {};  
class D : public  C {};  
int main()  
{  
    try  
    {  
        throw "ooops!";  
    }  
    catch( C ) {}  
    catch( D ) {}  // warning C4286, D is derived from C  
}  
```