---
title: "Compilerwarnung (Stufe 1) C4508"
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
  - "C4508"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4508"
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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