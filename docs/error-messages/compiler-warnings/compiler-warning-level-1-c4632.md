---
title: "Compilerwarnung (Stufe 1) C4632 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4632"
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 1) C4632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML\-Dokumentkommentar: Datei \- Zugriff verweigert: Grund  
  
 Der Pfad zur XDC\-Datei \(`file`\) war ungültig, und es wurde keine XDC\-Datei erstellt.  
  
 Im folgenden Beispiel wird C4632 generiert:  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```