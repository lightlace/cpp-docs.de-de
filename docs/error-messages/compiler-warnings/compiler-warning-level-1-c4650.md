---
title: "Compilerwarnung (Stufe 1) C4650 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4650"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4650"
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4650
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Debuginformationen nicht in vorkompilierter Headerdatei vorhanden; nur globale Symbole aus dieser Datei verfügbar  
  
 Die vorkompilierte Headerdatei wurde nicht mit symbolischen Debuginformationen von Microsoft kompiliert.  
  
 Nach dem Verknüpfen enthält die daraus resultierende ausführbare oder DLL\-Datei keine Debuginformationen für lokale Symbole aus dem vorkompilierten Header.  
  
 Sie vermeiden diese Warnung, indem Sie die vorkompilierte Headerdatei mit der Befehlszeilenoption [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) neu kompilieren.