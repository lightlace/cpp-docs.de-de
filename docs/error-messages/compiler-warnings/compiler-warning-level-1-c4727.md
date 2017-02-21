---
title: "Compilerwarnung (Stufe 1) C4727 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4727"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4727"
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Compilerwarnung (Stufe 1) C4727
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein vorkompilierter Header mit dem Namen PCH\-Datei und dem gleichen Zeitstempel wurde in OBJ\-Datei1 und in OBJ\-Datei2 gefunden.  Der zuerst gefundene wird verwendet.  
  
 C4727 tritt auf, wenn mehrere Kompiliereinheiten mit **\/Yc** kompiliert werden, und der Compiler nicht in der Lage ist, sämtliche OBJ\-Dateien mit demselben PCH\-Timestamp zu markieren.  
  
 Um das Problem zu beheben, kompilieren Sie eine Quelldatei mit **\/Yc \/c** \(hierbei wird eine PCH erstellt\), kompilieren Sie die anderen Quelldateien unabhängig davon mit **\/Yu \/c** \(hierbei wird die PCH verwendet\), und verknüpfen Sie sie miteinander.  
  
 Wenn Sie also Folgendes eingegeben haben und dabei C4727 generiert wurde:  
  
 **cl \/clr \/GL a.cpp b.cpp c.cpp \/Ycstdafx.h**  
  
 Geben Sie stattdessen Folgendes ein:  
  
 **cl \/clr \/GL a.cpp \/Ycstdafx.h \/c**  
  
 **cl \/clr \/GL b.cpp c.cpp \/Yustdafx.h \/link a.obj**  
  
 Weitere Informationen finden Sie unter  
  
-   [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md)  
  
-   [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md)