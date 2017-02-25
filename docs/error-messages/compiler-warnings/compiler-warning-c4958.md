---
title: "Compilerwarnung C4958 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4958"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4958"
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerwarnung C4958
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operation': Die Zeigerarithmetik kann nicht überprüft werden.  
  
 Bei Verwendung der Zeigerarithmetik wird ein nicht überprüfbares Image erstellt.  
  
 Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md)\-Pragmas oder der Compileroption [\/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.  
  
 Im folgenden Beispiel wird C4958 generiert:  
  
```  
// C4958.cpp // compile with: /clr:safe // #pragma warning( disable : 4958 ) using namespace System; int main( ) { Int32 arr[] = new Int32[10]; Int32* p = &arr[0]; p++;   // C4958 }  
```  
  
 Der Compiler implementiert Arrayoperationen mit Zeigerarithmetik. Daher sind systemeigene Arrays nicht überprüfbar. Verwenden Sie stattdessen ein CLR\-Array. Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C4958 generiert:  
  
```  
// C4958b.cpp // compile with: /clr:safe // #pragma warning( disable : 4958 ) int main() { int array[5]; array[4] = 0;   // C4958 }  
```