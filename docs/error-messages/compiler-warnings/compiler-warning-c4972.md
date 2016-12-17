---
title: "Compilerwarnung C4972"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4972"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4972"
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4972
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das direkte Ändern oder Behandeln des Ergebnisses eines Unboxing\-Vorgangs als L\-Wert kann nicht überprüft werden.  
  
 Das Dereferenzieren eines Handles für einen Werttyp \(auch als Unboxing bezeichnet\) und das anschließende Zuweisen ist nicht überprüfbar.  
  
 Weitere Informationen finden Sie unter [Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4972 generiert.  
  
```  
// C4972.cpp // compile with: /clr:safe using namespace System; ref struct R { int ^ p;   // a value type }; int main() { R ^ r = gcnew R; *(r->p) = 10;   // C4972 // OK r->p = 10; Console::WriteLine( r->p ); Console::WriteLine( *(r->p) ); }  
```