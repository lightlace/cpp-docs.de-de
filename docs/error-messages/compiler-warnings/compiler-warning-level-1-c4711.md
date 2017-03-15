---
title: "Compilerwarnung (Stufe 1) C4711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4711"
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktion "Funktion" ausgewählt für automatische Inline\-Erweiterung  
  
 Der Compiler hat die angegebene Funktion "inline" erweitert, obwohl diese nicht für die Inline\-Erweiterung gekennzeichnet war.  
  
 C4711 ist aktiviert, falls [\/Ob2](../../build/reference/ob-inline-function-expansion.md) angegeben wird.  
  
 Der Compiler entscheidet darüber, ob eine Inlinefunktion erweitert wird oder nicht.  Diese Warnung dient zu Informationszwecken.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Um eine Warnung zu aktivieren, verwenden Sie [\#pragma warning](../../preprocessor/warning.md).  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).