---
title: "Compilerfehler C3737 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3737"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3737"
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3737
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Delegat': ein Delegat hat möglicherweise keine explizite Aufrufkonvention  
  
 Sie können die [Aufrufkonvention](../../cpp/calling-conventions.md) für einen [\_\_delegate](../../misc/delegate.md) nicht festlegen.  
  
 Im folgenden Beispiel wird C3737 generiert:  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
  
 Im folgenden Beispiel wird C3737 generiert:  
  
```  
// C3737b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// __delegate void MyFunc();  
  
int main() {  
}  
```