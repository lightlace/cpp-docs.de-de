---
title: "Compilerfehler C2199 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2199"
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: 'Bezeichner \(' im globalen Gültigkeitsbereich gefunden \(war eine Deklaration beabsichtigt?\)  
  
 Der angegebene Kontext verursachte einen Syntaxfehler.  Die Deklarationssyntax könnte fehlerhaft sein.  
  
 Im folgenden Beispiel wird C2199 generiert:  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```