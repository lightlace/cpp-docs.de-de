---
title: .EXP-Dateien als Eingabe für den Linker
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
ms.openlocfilehash: 4f70aad2fa91431da771f8e5be47956ae2db45a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661930"
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker

Exportdateien (.exp) enthalten Informationen zu den exportierten Funktionen und Daten-Elementen. Wenn LIB eine Importbibliothek erstellt wird, wird auch eine .exp-Datei. Verwenden Sie die EXP-Datei, wenn Sie ein Programm, die exportiert verknüpfen in und aus einem anderen Programm importiert wird, entweder direkt oder indirekt. Wenn Sie eine mit einer EXP-Datei Verknüpfung, ergibt LINK keine Importbibliothek, da es wird davon ausgegangen, dass LIB noch nicht erstellt. Details zu .exp-Dateien und Importbibliotheken, finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)