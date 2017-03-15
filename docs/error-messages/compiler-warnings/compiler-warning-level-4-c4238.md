---
title: "Compilerwarnung (Stufe 4) C4238 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4238"
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 4) C4238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: R\-Wert einer Klasse als L\-Wert verwendet  
  
 Um Kompatibilität mit früheren Versionen von Visual C\+\+ zu gewährleisten, ermöglichen es die Microsoft\-Erweiterungen \(**\/Ze**\), einen Klassentyp in einem Kontext, in dem seine Adresse implizit oder explizit übernommen wird, als R\-Wert zu verwenden.  Dies kann sich jedoch in einigen Fällen, z. B. im folgenden Beispiel, als riskant erweisen.  
  
## Beispiel  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) resultiert aus dieser Verwendungsweise ein Fehler.