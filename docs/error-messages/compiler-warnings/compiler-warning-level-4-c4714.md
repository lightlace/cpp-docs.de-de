---
title: Compilerwarnung (Stufe 4) C4714 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0f327e7ffc5d2fe00abe3c0845af10a846243bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295417"
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