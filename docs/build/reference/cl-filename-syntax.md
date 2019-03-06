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
ms.openlocfilehash: d2dd51370fd346c4cd7dad7bb97bfa76a9f759d9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420725"
---
# <a name="cl-filename-syntax"></a>Syntax für Dateinamen bei CL

CL akzeptiert Dateinamen, die FAT-, HPFS- oder NTFS-Namenskonventionen entsprechen. Jeder Dateiname kann einen vollständigen oder teilweisen Pfad umfassen. Ein vollständiger Pfad enthält einen Laufwerksnamen sowie einen oder mehrere Verzeichnisnamen. CL akzeptiert Dateinamen getrennt durch Backslash (\\) oder Schrägstriche (/). Dateinamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden. Ein partieller Pfad lässt den Servernamen weg, den CL als das aktuelle Laufwerk ansieht. Wenn Sie einen Pfad angeben, nimmt CL an, dass die Datei im aktuellen Verzeichnis ist.

Die Dateierweiterung bestimmt, wie Dateien verarbeitet werden. C- und C++-Dateien, die die Erweiterung .c, .cxx oder .cpp haben, werden kompiliert. Andere Dateien, einschließlich .obj-Dateien, Bibliotheken (.lib) und Moduldefinitionsdateien (.def)-Dateien, werden unverarbeitet an den Linker übergeben.

## <a name="see-also"></a>Siehe auch

[Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)
