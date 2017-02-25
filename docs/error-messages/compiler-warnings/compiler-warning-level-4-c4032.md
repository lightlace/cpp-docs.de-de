---
title: "Compilerwarnung (Stufe 4) C4032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4032"
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der formale Parameter 'Nummer' hat nach der Erweiterung einen anderen Typ  
  
 Der Parametertyp ist aufgrund von standardmäßigen Erweiterungen nicht mit dem Typ aus einer früheren Deklaration kompatibel.  
  
 Bei Einhaltung von ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) resultiert daraus ein Fehler und bei Verwendung der Microsoft\-Erweiterungen \(\/Ze\) eine Warnung.  
  
## Beispiel  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```