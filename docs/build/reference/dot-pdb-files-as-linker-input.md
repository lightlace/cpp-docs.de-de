---
title: . PDB-Dateien als Linkereingabe | Microsoft-Dokumentation
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
ms.openlocfilehash: d6b728903d2a270efc6b3eb736e45540651dae8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706185"
---
# <a name="pdb-files-as-linker-input"></a>PDB-Dateien als Eingabe für den Linker

Objektdateien Sie (obj)-Dateien kompiliert, mit der Option "/ Zi" den Namen einer Programmdatenbank (PDB) enthalten. Sie geben nicht den Namen des Objekts PDB-Datei an den Linker; LINK wird der eingebettete Name verwendet, die PDB-Datei gefunden wird, wenn sie benötigt wird. Dies gilt auch für Debugfähige Objekte in einer Bibliothek zu finden; die PDB-Datei für eine Debugfähige Bibliothek muss an den Linker zusammen mit der Bibliothek verfügbar sein.

LINK verwendet auch eine PDB-Datei, um Debuginformationen für die .exe-Datei oder DLL-Datei zu speichern. Des Programms PDB ist sowohl eine Ausgabedatei eine Eingabedatei, da LINK die PDB-Datei aktualisiert, wenn sie das Programm neu erstellt.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)