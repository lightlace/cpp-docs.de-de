---
title: "Compilerwarnung (Stufe 3) C4638"
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
  - "C4638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4638"
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML\-Dokumentkommentarziel: Verweis auf unbekanntes Symbol 'Symbol'.  
  
 Der Compiler konnte ein Symbol nicht auflösen \(***Symbol***\). Das Symbol muss in der Kompilierung gültig sein.  
  
 Im folgenden Beispiel wird C4638 generiert:  
  
```  
// C4638.cpp // compile with: /clr /doc /LD /W3 using namespace System; /// Text for class MyClass. public ref class MyClass { public: /// <summary> Text </summary> /// <see cref="aSymbolThatAppearsNowhereInMyProject"/> // Try the following line instead: // /// <see cref="System::Console::WriteLine"/> void MyMethod() {} };   // C4638  
```