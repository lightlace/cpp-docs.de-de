---
title: "Compilerwarnung C4957"
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
  - "C4957"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4957"
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung C4957
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'CAST' : Die explizite Umwandlung von 'cast\_from' in 'cast\_to' kann nicht überprüft werden  
  
 Eine Umwandlung ergibt ein nicht überprüfbares Image.  
  
 Einige Umwandlungen sind sicher \(z. B. eine `static_cast` die benutzerdefinierte Umwandlungen auslöst, und eine `const_cast`\). Eine [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) generiert auf jeden Fall überprüfbaren Code.  
  
 Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md)\-Pragmas oder der Compileroption [\/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.  
  
 Im folgenden Beispiel wird C4957 generiert:  
  
```  
// C4957.cpp // compile with: /clr:safe // #pragma warning( disable : 4957 ) using namespace System; int main() { Object ^ o = "Hello, World!"; String ^ s = static_cast<String^>(o);   // C4957 String ^ s2 = safe_cast<String^>(o);   // OK }  
```