---
title: "Compilerwarnung C4746 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 2
---
# Compilerwarnung C4746
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

flüchtiger Zugriff '\<des Ausdrucks\>' hängt von \/volatile: \[ISO&#124;Frau\] Einstellung; Betrachten Sie mit \_\_iso\_volatile\_load\-\/storesysteminterner funktionen.  
  
 C4746 wird ausgegeben, wenn auf eine flüchtige Variable direkt zugegriffen wird.  Es soll, um Entwicklern zu helfen, Codespeicherorte zu identifizieren, die durch das bestimmte aktuell eingestellte Modell für flüchtigen verliert betroffen sind \(das mit der Compileroption [\/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) gesteuert werden kann\).  Insbesondere kann es nützlich sein, bei der vom Compiler generierte Hardwarearbeitsspeicherbarrieren lokalisiert, wenn \/volatile:ms verwendet wird.  
  
 Die \_\_iso\_volatile\_load\-\/storesysteminternen funktionen können verwendet werden, um für flüchtigen Speicher explizit zugreifen, ohne über das Modell für flüchtigen verliert beeinflusst werden.  Verwenden dieser systeminternen Funktionen löst nicht C4746 aus.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).