---
title: "Compilerwarnung C4956 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4956"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4956"
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung C4956
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typ': Dieser Typ ist nicht überprüfbar  
  
 Diese Warnung wird generiert, wenn [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) angegeben ist und Ihr Code einen Typ enthält, der nicht überprüfbar ist.  
  
 Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md)\-Pragmas oder der Compileroption [\/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.  
  
 Im folgenden Beispiel wird C4956 generiert:  
  
```  
// C4956.cpp // compile with: /clr:safe int* p;   // C4956  
```