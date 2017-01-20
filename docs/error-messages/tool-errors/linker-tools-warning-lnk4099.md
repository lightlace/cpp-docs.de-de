---
title: "Linkertoolwarnung LNK4099"
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
  - "LNK4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4099"
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PDB 'Dateiname' wurde nicht mit 'Objekt\/Bibliothek' oder an 'Pfad' gefunden; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären  
  
 Der Linker konnte die PDB\-Datei nicht finden.  Kopieren Sie sie in das Verzeichnis, in dem sich `object/library` befindet.  
  
 So finden Sie den Namen der der Objektdatei zugeordneten PDB\-Datei:  
  
1.  Extrahieren Sie mit [lib](../../build/reference/lib-reference.md) **\/extract:**`objectname`**.obj** `xyz`**.lib** eine Objektdatei aus der Bibliothek.  
  
2.  Überprüfen Sie mit **dumpbin \/section:.debug$T \/rawdata** `objectname`**.obj** den Pfad zur PDB\-Datei.  
  
 Sie können auch mit [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) kompilieren, sodass die PDB\-Datei nicht verwendet werden muss, oder die Linkeroption [\/DEBUG](../../build/reference/debug-generate-debug-info.md) entfernen, wenn Sie über keine PDB\-Dateien für die zu verknüpfenden Objekte verfügen.