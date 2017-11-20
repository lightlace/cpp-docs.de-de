---
title: "Compilerwarnung (Stufe 1) C4508 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4508"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4508"
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4508
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Funktion sollte einen Wert zurückgeben; Ergebnistyp 'void' angenommen  
  
 Für die Funktion wurde kein Rückgabetyp angegeben.  In diesem Fall wird C4430 ebenfalls ausgelöst, und der Compiler implementiert die für C4430 gemeldete Lösung \(Standardwert ist int\).  
  
 Um diese Warnung zu vermeiden, sollten Sie den Rückgabetyp von Funktionen explizit deklarieren.  
  
 Im folgenden Beispiel wird C4508 generiert:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```