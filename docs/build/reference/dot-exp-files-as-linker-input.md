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
ms.openlocfilehash: 0f2f5c22752d6d938700228fc208c21b8f32cc7b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822287"
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker

Exportdateien (.exp) enthalten Informationen zu den exportierten Funktionen und Daten-Elementen. Wenn LIB eine Importbibliothek erstellt wird, wird auch eine .exp-Datei. Verwenden Sie die EXP-Datei, wenn Sie ein Programm, die exportiert verknüpfen in und aus einem anderen Programm importiert wird, entweder direkt oder indirekt. Wenn Sie eine mit einer EXP-Datei Verknüpfung, ergibt LINK keine Importbibliothek, da es wird davon ausgegangen, dass LIB noch nicht erstellt. Details zu .exp-Dateien und Importbibliotheken, finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](link-input-files.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
