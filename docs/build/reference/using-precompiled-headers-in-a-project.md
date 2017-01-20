---
title: "Verwenden von vorkompilierten Headern in einem Projekt"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vorkompilierte Headers"
ms.assetid: 95010260-a035-4327-9d61-222016ac146c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von vorkompilierten Headern in einem Projekt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die vorangehenden Abschnitte enthielten eine Übersicht über die Optionen **\/Yc** und **\/Yu** für vorkompilierte Header, die **\/Fp**\-Option sowie über das [hdrstop](../../preprocessor/hdrstop.md)\-Pragma.  In diesem Abschnitt wird die Verwendung der manuellen Optionen für vorkompilierte Header in einem Projekt beschrieben. Der Abschnitt endet mit einem Makefilebeispiel einschließlich des verwalteten Codes.  
  
 Weitere Ansätze zur Verwendung der manuellen Optionen für vorkompilierte Header finden Sie in den Makefiles im Verzeichnis **MFC\\SRC**, das bei der Standardinstallation von Visual C\+\+ erstellt wird.  In diesen Makefiles wird eine Methode verwendet, die mit der in diesem Abschnitt vergleichbar ist. Es wird jedoch stärkere Betonung auf das **NMAKE**\-Makro \(Microsoft Program Maintenance Utility\) sowie auf die Steuerung des Erstellungsvorgangs gelegt.  
  
 Dieser Abschnitt enthält die folgenden Themen:  
  
-   [PCH\-Dateien im Erstellungsvorgang](../../build/reference/pch-files-in-the-build-process.md)  
  
-   [Beispielmakefile für PCH](../../build/reference/sample-makefile-for-pch.md)  
  
-   [Beispielcode für PCH](../../build/reference/example-code-for-pch.md)  
  
## Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)