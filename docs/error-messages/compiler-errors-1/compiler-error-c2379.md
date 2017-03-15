---
title: "Compilerfehler C2379 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2379"
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der formale Parameter Nummer hat nach der Erweiterung einen anderen Typ  
  
 Der Typ des angegebenen Parameters ist durch standardmäßige Erweiterungen nicht mit dem Typ aus einer früheren Deklaration kompatibel.  Dies ist ein Fehler in ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) und eine Warnung bei Verwendung der Microsoft\-Erweiterungen \(**\/Ze**\).  
  
 Im folgenden Beispiel wird C2379 generiert:  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```