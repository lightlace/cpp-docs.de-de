---
title: "Linkertoolfehler LNK1158"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1158"
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Dateiname' kann nicht ausgeführt werden  
  
 Die von [LINK](../../build/reference/linker-command-line-syntax.md) aufgerufene ausführbare Datei befindet sich weder im selben Verzeichnis wie LINK noch in einem in der **PATH**\-Umgebungsvariablen angegebenen Verzeichnis.  
  
 Dieser Fehler wird z. B. beim Versuch ausgegeben, den **PGOPTIMIZE**\-Parameter mit der [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)\-Linkeroption auf einem Computer mit einem 32\-Bit\-Betriebssystem zu verwenden.