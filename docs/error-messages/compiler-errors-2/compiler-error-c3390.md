---
title: "Compilerfehler C3390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3390"
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typargument": Ungültiges Typargument für den generischen Parameter "Param" von "generischer\_Typ" \(generisch\). Muss ein Referenztyp sein.  
  
 Ein generischer Typ wurde fehlerhaft instanziiert.  Überprüfen Sie die Typdefinition.  Weitere Informationen finden Sie unter [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird mit C\# eine Komponente erstellt, die einen generischen Typ mit bestimmten Einschränkungen enthält, die nicht unterstützt werden, wenn generische Typen in [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)] geschrieben werden. Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
```  
// C3390.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3390 generiert:  
  
```  
// C3390_b.cpp // compile with: /clr #using <C3390.dll> ref class R { R(int) {} }; value class V {}; ref struct N { N() {} }; int main () { GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type GR<R^, V, N^>^ gr2b;   // OK }  
```