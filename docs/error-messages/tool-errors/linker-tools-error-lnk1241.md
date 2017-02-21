---
title: "Linkertoolfehler LNK1241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolfehler LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Ressourcendatei 'Ressourcendatei' wurde bereits angegeben  
  
 Dieser Fehler wird erzeugt, wenn Sie **cvtres** manuell über die Befehlszeile ausführen und anschließend die resultierende OBJ\-Datei zusätzlich zu weiteren RES\-Dateien an den Linker übergeben.  
  
 Um mehrere RES\-Dateien anzugeben, übergeben Sie sämtliche Dateien als RES\-Dateien an den Linker, also nicht innerhalb der von **cvtres** erstellten OBJ\-Dateien.