---
title: "Compilerfehler C3385"
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
  - "C3385"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3385"
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3385
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse::Funktion': Eine Funktion, die ein benutzerdefiniertes DllImport\-Attribut hat, kann keine Instanz einer Klasse zurückgeben.  
  
 Eine Funktion, die als Teil einer DLL\-Datei definiert wird, die mit dem `DllImport`\-Attribut angegeben wurde, kann keine Instanz einer Klasse zurückgeben.  
  
 Im folgenden Beispiel wird C3385 generiert:  
  
```  
// C3385.cpp // compile with: /clr /c using namespace System; using namespace System::Runtime::InteropServices; struct SomeStruct1 {}; public ref struct Wrap { [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ] static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385 };  
```  
  
 Im folgenden Beispiel wird C3385 generiert:  
  
```  
// C3385_2.cpp // compile with: /clr:oldSyntax /c using namespace System; using namespace System::Runtime::InteropServices; struct SomeStruct1 {}; public __gc struct Wrap { [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ] static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385 };  
```