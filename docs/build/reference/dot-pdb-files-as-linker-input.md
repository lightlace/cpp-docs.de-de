---
title: PDB-Dateien als Eingabe für den Linker
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 365f2955f5bc9e8082221a070af454c820c665f1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822509"
---
# <a name="pdb-files-as-linker-input"></a>PDB-Dateien als Eingabe für den Linker

Objektdateien Sie (obj)-Dateien kompiliert, mit der Option "/ Zi" den Namen einer Programmdatenbank (PDB) enthalten. Sie geben nicht den Namen des Objekts PDB-Datei an den Linker; LINK wird der eingebettete Name verwendet, die PDB-Datei gefunden wird, wenn sie benötigt wird. Dies gilt auch für Debugfähige Objekte in einer Bibliothek zu finden; die PDB-Datei für eine Debugfähige Bibliothek muss an den Linker zusammen mit der Bibliothek verfügbar sein.

LINK verwendet auch eine PDB-Datei, um Debuginformationen für die .exe-Datei oder DLL-Datei zu speichern. Des Programms PDB ist sowohl eine Ausgabedatei eine Eingabedatei, da LINK die PDB-Datei aktualisiert, wenn sie das Programm neu erstellt.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](link-input-files.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
