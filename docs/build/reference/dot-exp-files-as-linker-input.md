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
ms.openlocfilehash: 170adfe54b34d14f84b54c717bc9f75fe0b7ab37
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418476"
---
# <a name="exp-files-as-linker-input"></a>.EXP-Dateien als Eingabe für den Linker

Exportdateien (.exp) enthalten Informationen zu den exportierten Funktionen und Daten-Elementen. Wenn LIB eine Importbibliothek erstellt wird, wird auch eine .exp-Datei. Verwenden Sie die EXP-Datei, wenn Sie ein Programm, die exportiert verknüpfen in und aus einem anderen Programm importiert wird, entweder direkt oder indirekt. Wenn Sie eine mit einer EXP-Datei Verknüpfung, ergibt LINK keine Importbibliothek, da es wird davon ausgegangen, dass LIB noch nicht erstellt. Details zu .exp-Dateien und Importbibliotheken, finden Sie unter [arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
