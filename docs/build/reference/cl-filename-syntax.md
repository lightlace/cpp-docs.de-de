---
title: Syntax für Dateinamen bei CL
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: 929096ed169a33e0876c3afb68f3594757d61e4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438934"
---
# <a name="cl-filename-syntax"></a>Syntax für Dateinamen bei CL

CL akzeptiert Dateinamen, die FAT-, HPFS- oder NTFS-Namenskonventionen entsprechen. Jeder Dateiname kann einen vollständigen oder teilweisen Pfad umfassen. Ein vollständiger Pfad enthält einen Laufwerksnamen sowie einen oder mehrere Verzeichnisnamen. CL akzeptiert Dateinamen getrennt durch Backslash (\\) oder Schrägstriche (/). Dateinamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden. Ein partieller Pfad lässt den Servernamen weg, den CL als das aktuelle Laufwerk ansieht. Wenn Sie einen Pfad angeben, nimmt CL an, dass die Datei im aktuellen Verzeichnis ist.

Die Dateierweiterung bestimmt, wie Dateien verarbeitet werden. C- und C++-Dateien, die die Erweiterung .c, .cxx oder .cpp haben, werden kompiliert. Andere Dateien, einschließlich .obj-Dateien, Bibliotheken (.lib) und Moduldefinitionsdateien (.def)-Dateien, werden unverarbeitet an den Linker übergeben.

## <a name="see-also"></a>Siehe auch

[Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)