---
title: Compilerwarnung (Stufe 4) C4714 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d49ff1bbf6538965d277b0afdd6c96fd9c71ef0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4714"></a>Compilerwarnung (Stufe 4) C4714
'Funktion' als __forceinline markiert nicht inline  
  
 Die angegebene Funktion für die Inlineerweiterung ausgewählt wurde, aber der Compiler hat nicht ausgeführt, das inlining.  
  
 Obwohl `__forceinline` stärker an den Compiler als `__inline`, inlining erfolgt immer noch nach Ermessen des Compilers, jedoch keine Heuristik werden verwendet, um zu bestimmen, die Vorteile von inlining dieser Funktion.  
  
 In einigen Fällen der Compiler wird nicht Inline eine bestimmte Funktion mechanische Gründen. Beispielsweise wird der Compiler nicht Inline:  
  
-   Eine Funktion, wenn sie zu mischen von SEH und C++ EH führen würde.  
  
-   Einige Funktionen für die Kopie erstellt Objekte, die als Wert übergeben wird, wenn - GX/EHs/EHa aktiviert ist.  
  
-   Funktionen, die ein entladbarer Objekt nach Wert zurückgeben, wenn - GX/EHs/EHa aktiviert ist.  
  
-   Funktionen mit der Inlineassembly beim Kompilieren ohne - Benutzeranmeldung/Ox/O1/O2.  
  
-   Funktionen mit einer Liste variabler Argumente.  
  
-   Eine Funktion mit einem **versuchen** -Anweisung (C++-Ausnahmebehandlung).  
  
 Im folgenden Beispiel wird C4714 generiert:  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```