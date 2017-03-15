---
title: "Schwerwiegender Fehler C1016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1016"
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Schwerwiegender Fehler C1016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#ifdef erwartet einen Bezeichner\#ifndef erwartet einen Bezeichner \(\#ifdef expected an identifier\#ifndef expected an identifier\)  
  
 In der Direktive für die bedingte Kompilierung \([\#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) oder `#ifndef`\) fehlt ein Bezeichner für die Auswertung. Geben Sie einen Bezeichner an, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C1016 generiert:  
  
```  
// C1016.cpp #ifdef   // C1016 #define FC1016 #endif int main() {}  
```  
  
 Mögliche Lösung:  
  
```  
// C1016b.cpp #ifdef X #define FC1016 #endif int main() {}  
```