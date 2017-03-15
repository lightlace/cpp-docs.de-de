---
title: "Compilerwarnung (Stufe 1) C4944 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4944"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4944"
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4944
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': Das Symbol kann nicht aus 'assembly1' importiert werden, da 'symbol' im aktuellen Gültigkeitsbereich bereits vorhanden ist  
  
 Es wurde ein Symbol in einer Quellcodedatei definiert, und dann wurde in einer \#using\-Anweisung auf eine Assembly verwiesen, die das Symbol ebenfalls definiert. Das Symbol in der Assembly wird ignoriert.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Komponente mit einem Typ namens 'ClassA' erstellt.  
  
```  
// C4944.cs // compile with: /target:library // C# source code to create a dll public class ClassA { public int i; }  
```  
  
## Beispiel  
 In den folgenden Beispielen wird C4944 generiert:  
  
```  
// C4944b.cpp // compile with: /clr /W1 class ClassA { public: int u; }; #using "C4944.dll"   // C4944 ClassA also defined C4944.dll int main() { ClassA * x = new ClassA(); x->u = 9; System::Console::WriteLine(x->u); }  
```