---
title: "Compilerwarnung (Stufe 4) C4205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4205"
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Deklaration einer statischen Funktion in einer Funktion  
  
 Bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\) können **static**\-Funktionen innerhalb einer anderen Funktion deklariert werden.  Die Funktion gehört dennoch zum globalen Gültigkeitsbereich.  
  
## Beispiel  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 Derartige Initialisierungen sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.