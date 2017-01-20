---
title: "Schwerwiegender Fehler C1051"
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
  - "C1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1051"
ms.assetid: 87dcbd3b-0952-499a-bd42-64f9e8de2605
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Programmdatenbankdatei 'pdbfile' hat ein veraltetes Format. Löschen Sie sie, und starten Sie die Kompilierung erneut.  
  
 Der Compiler kann die Programmdatenbankdatei nicht aktualisieren, da sie eine ältere Versionsnummer besitzt.  Löschen Sie die Datei, und kompilieren Sie das Programm neu mit **\/Zi** oder **\/ZI**.  Weitere Informationen finden Sie unter [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md)