---
title: "Compilerwarnung (Stufe 1) C4615 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4615"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4615"
ms.assetid: 7b107c01-0da2-4e01-8b40-93813e30b94c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4615
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma\-Warnung: Unbekannter Typ der Benutzerwarnung  
  
 Mit **pragma** [warning](../../preprocessor/warning.md) wurde ein ungültiger Bezeichner für Warnungen angegeben.  Verwenden Sie einen gültigen Bezeichner, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C4615 generiert:  
  
```  
// C4615.cpp  
// compile with: /W1 /LD  
#pragma warning(enable : 4401)   // C4615, 'enable' not valid specifier  
  
// use the code below to resolve the error  
// #pragma warning(default : 4401)  
```