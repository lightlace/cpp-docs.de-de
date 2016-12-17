---
title: "Compilerwarnung C4959"
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
  - "C4959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4959"
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Struktur "type" \(nicht verwaltet\) in \/clr:safe kann nicht definiert werden, da durch den Zugriff auf die Member nicht überprüfbarer Code ausgegeben wird  
  
 Das Zugreifen auf einen Member eines nicht verwalteten Typs resultiert in einem nicht überprüfbaren Abbild \(peverify.exe\).  
  
 Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md)\-Pragmas oder der Compileroption [\/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.  
  
 Im folgenden Beispiel wird C4959 generiert:  
  
```  
// C4959.cpp // compile with: /clr:safe // Uncomment the following line to resolve. // #pragma warning( disable : 4959 ) struct X { int data; }; int main() { X x; x.data = 10;   // C4959 }  
```