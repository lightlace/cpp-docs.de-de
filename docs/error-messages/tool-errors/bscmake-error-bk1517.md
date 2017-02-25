---
title: "BSCMAKE-Fehler BK1517 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1517"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1517"
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# BSCMAKE-Fehler BK1517
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quelldatei für SBR\-Datei wurde sowohl mit \/Yc als auch \/Yu kompiliert  
  
 Die SBR\-Datei verweist auf sich selbst.  Sie wurde möglicherweise mit **\/Yu** neu kompiliert, nachdem sie mit **\/Yc** kompiliert wurde.  Setzen Sie die Compileroptionen für die Quelldatei zurück auf **\/Yc**. Wählen Sie dann **Neu erstellen** aus, um neue SBR\-Dateien zu generieren.  Kompilieren Sie die Quelldatei nicht mit **\/Yu** neu.