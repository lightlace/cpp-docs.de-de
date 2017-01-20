---
title: "Linkertoolfehler LNK1241"
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
  - "LNK1241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1241"
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Ressourcendatei 'Ressourcendatei' wurde bereits angegeben  
  
 Dieser Fehler wird erzeugt, wenn Sie **cvtres** manuell über die Befehlszeile ausführen und anschließend die resultierende OBJ\-Datei zusätzlich zu weiteren RES\-Dateien an den Linker übergeben.  
  
 Um mehrere RES\-Dateien anzugeben, übergeben Sie sämtliche Dateien als RES\-Dateien an den Linker, also nicht innerhalb der von **cvtres** erstellten OBJ\-Dateien.