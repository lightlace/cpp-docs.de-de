---
title: "Linkertoolfehler LNK1158 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1158"
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Dateiname' kann nicht ausgeführt werden  
  
 Die von [LINK](../../build/reference/linker-command-line-syntax.md) aufgerufene ausführbare Datei befindet sich weder im selben Verzeichnis wie LINK noch in einem in der **PATH**\-Umgebungsvariablen angegebenen Verzeichnis.  
  
 Dieser Fehler wird z. B. beim Versuch ausgegeben, den **PGOPTIMIZE**\-Parameter mit der [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\-Linkeroption auf einem Computer mit einem 32\-Bit\-Betriebssystem zu verwenden.