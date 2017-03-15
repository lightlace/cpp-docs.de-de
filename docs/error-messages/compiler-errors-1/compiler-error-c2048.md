---
title: "Compilerfehler C2048 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2048"
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mehrere Vorkommen von default  
  
 Eine `switch`\-Anweisung enthält mehrere `default`\-Bezeichnungen. Löschen Sie eine der `default`Bezeichnungen, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2048 generiert:  
  
```  
// C2048.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; default:   // C2048 a = 3; } }  
```  
  
 Mögliche Lösung:  
  
```  
// C2048b.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; } }  
```