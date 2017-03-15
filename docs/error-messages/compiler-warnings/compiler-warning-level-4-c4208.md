---
title: "Compilerwarnung (Stufe 4) C4208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4208"
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: delete \[Ausdruck\] \- Ausdruck ausgewertet, aber ignoriert  
  
 Bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\) können Sie ein Array durch einen in eckigen Klammern eingeschlossenen Wert mit dem [Operator "delete"](../../cpp/delete-operator-cpp.md) löschen.  Der Wert wird ignoriert.  
  
```  
// C4208.cpp  
// compile with: /W4  
int main()  
{  
   int * MyArray = new int[18];  
   delete [18] MyArray;      // C4208  
   MyArray = new int[18];  
   delete [] MyArray;        // ok  
}  
```  
  
 Derartige Werte sind bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) ungültig.