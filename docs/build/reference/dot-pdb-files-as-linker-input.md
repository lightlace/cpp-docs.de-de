---
title: . PDB-Dateien als Linkereingabe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6707be955b5c4a332d1162f53b1cb854391a2ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pdb-files-as-linker-input"></a>PDB-Dateien als Eingabe für den Linker
Objektdateien Sie (.obj)-Dateien, die Kompilierung mit/ZI-Option den Namen des eine Programmdatenbank (PDB) enthalten. Sie nicht den Namen des Objekts PDB-Datei an den Linker angeben; LINK verwendet den eingebetteten Namen die PDB-Datei zu finden, wenn er benötigt wird. Dies gilt auch für Debugfähige Objekte in einer Bibliothek; die PDB-Datei für eine debugfähigen Bibliothek muss an den Linker zusammen mit der Bibliothek verfügbar sein.  
  
 LINK verwendet auch eine PDB-Datei, um Debuginformationen für die .exe oder .dll-Datei zu speichern. Das Programm PDB ist eine Ausgabedatei und eine Eingabedatei, da LINK die PDB-Datei aktualisiert, wenn sie das Programm neu erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [LINK-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)