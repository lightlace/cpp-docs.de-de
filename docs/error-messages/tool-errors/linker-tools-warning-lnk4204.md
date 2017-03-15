---
title: "Linkertoolwarnung LNK4204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4204"
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Linkertoolwarnung LNK4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Für 'Dateiname' sind keine Debuginformationen für das verweisende Modul vorhanden. Das Objekt wird ohne Debuginformationen verknüpft.  
  
 Die PDB\-Datei hat eine fehlerhafte Signatur.  Der Linker verknüpft das Objekt ohne Debuginformationen.  Sie können das Objekt auch mit der [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option neu kompilieren.  
  
 LNK4204 kann auftreten, wenn einige Objekte in der Bibliothek auf eine Datei verweisen, die nicht mehr vorhanden ist.  Dies kann z. B. passieren, wenn Sie die Projektmappe neu erstellen. Eine Objektdatei kann gelöscht und aufgrund eines Kompilierungsfehlers nicht neu erstellt werden.  Kompilieren Sie in diesem Fall mit **\/Z7** oder **\/Fd**, um die Objekte zu aktualisieren, sodass diese auf eine einzelne Datei pro Bibliothek verweisen \(wobei diese nicht den Standardnamen der PDB\-Datei hat\).  Weitere Informationen finden Sie unter [\/Fd \(Programmdatenbank\-Dateiname\)](../../build/reference/fd-program-database-file-name.md).  Vergewissern Sie sich, dass die PDB\-Datei bei jeder Aktualisierung durch das Quellsteuerungssystem mit der Bibliothek gespeichert wird.