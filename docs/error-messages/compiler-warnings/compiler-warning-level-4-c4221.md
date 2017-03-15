---
title: "Compilerwarnung (Stufe 4) C4221 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4221"
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: 'Bezeichner': Initialisierung mit der Adresse der automatischen Variable nicht möglich  
  
 Bei Verwendung der Microsoft\-Standarderweiterungen \(\/Ze\) können Sie einen Aggregattyp \(**array**, `struct` oder **union**\) mit der Adresse lokaler \(automatischer\) Variablen initialisieren.  
  
## Beispiel  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 Derartige Initialisierungen sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.