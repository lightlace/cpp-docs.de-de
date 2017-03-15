---
title: "Zwei Methoden f&#252;r das Vorkompilieren von Code | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien"
  - ".pch-Dateien, Vorkompilieren von Optionen"
  - "Automatisches Vorkompilieren"
  - "Code, Vorkompilieren"
  - "Kompilieren von Quellcode, Vorkompilieren"
  - "PCH-Dateien"
  - "PCH-Dateien, Vorkompilieren von Optionen"
  - "Vorkompilierte Headerdateien"
  - "Vorkompilierte Headerdateien, Vorkompilieren von Optionen"
  - "Vorkompilieren von Code"
ms.assetid: f50ac76f-e2a2-462d-bda5-0e2ab7cccdeb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Zwei Methoden f&#252;r das Vorkompilieren von Code
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit Visual C\+\+ können Sie beliebigen C\- oder C\+\+\-Code vorkompilieren; Sie sind nicht auf das Vorkompilieren von Headerdateien beschränkt.  
  
 Das Vorkompilieren erfordert Planung, es werden jedoch bedeutend schnellere Kompilierungen erreicht, wenn Sie Quellcode, bei dem es sich nicht um einfache Headerdateien handelt, vorkompilieren.  
  
 Kompilieren Sie Code vor, wenn Sie wissen, dass die Quelldateien gemeinsame Headerdateien verwenden, diese aber nicht in derselben Reihenfolge einfügen, oder wenn Sie Quellcode in die Vorkompilierung einbeziehen möchten.  
  
 Die Optionen für vorkompilierte Headerdateien sind [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md) und [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md).  Verwenden **\/Yc**, um einen vorkompilierten Header zu erstellen.  Bei Verwendung des optionalen `hdrstop`\-Pragmas können Sie über **\/Yc** Headerdateien und Quellcode vorkompilieren.  Wählen Sie **\/Yu**, um eine bereits vorhandene vorkompilierte Headerdatei in der bestehenden Kompilierung zu verwenden.  Außerdem kann **\/Fp** mit den Optionen **\/Yc** und **\/Yu** verwendet werden, um einen alternativen Namen für die vorkompilierte Headerdatei anzugeben.  
  
 In den Referenzthemen der Compileroptionen für **\/Yu** und **\/Yc** wird erläutert, wie in der Entwicklungsumgebung auf diese Funktionalität zugegriffen werden kann.  
  
## Weitere Informationen  
  
-   [Wann sollte Quellcode vorkompiliert werden?](../../build/reference/when-to-precompile-source-code.md)  
  
-   [Konsistenzregeln für vorkompilierte Header](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [Verwenden von vorkompilierten Headern in einem Projekt](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 Weitere Beispiele zur Verwendung von vorkompilierten Headern finden Sie in den Makefiles für die Programmbeispiele, die mit Microsoft Foundation Class Library ausgeliefert werden.  
  
## Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)