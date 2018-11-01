---
title: LINK-Eingabedateien
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: a5aaf162a16b6989ac1abbcb6a574af1c31b543a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550552"
---
# <a name="link-input-files"></a>LINK-Eingabedateien

Sie bieten den Linker Dateien, die Objekte, Import und standard-Bibliotheken, Ressourcen, Moduldefinitionen und Eingabe-Befehl enthalten. LINK verwendet Dateierweiterungen keine Annahmen zum Inhalt einer Datei. Stattdessen untersucht LINK jede Eingabedatei, um festzustellen, welche Art von Datei vorliegt.

Objektdateien in der Befehlszeile sind in der Reihenfolge verarbeitet, die sie in der Befehlszeile angezeigt werden. Bibliotheken werden in Reihenfolge durchsucht, über die Befehlszeile, mit der folgenden Einschränkung: nicht aufgelöste Symbole, beim Importieren einer Objektdatei aus einer Bibliothek in dieser Bibliothek zuerst gesucht, und klicken Sie dann die folgenden Bibliotheken aus der Befehlszeile und [DEFAULTLIB (Angeben von Standard-Bibliothek)](../../build/reference/defaultlib-specify-default-library.md) Anweisungen, und klicken Sie dann auf die Bibliotheken am Anfang der Befehlszeile aus.

> [!NOTE]
>  LINK akzeptiert eine durch Semikolons (oder jedes andere Zeichen) nicht mehr als Anfang eines Kommentars in Antwortdateien und ordnen Sie Dateien an. Semikolons sind nur als Anfang eines Kommentars in Moduldefinitionsdateien (.def) erkannt.

LINK wird die folgenden Typen von Eingabedateien verwendet:

- [OBJ-Dateien](../../build/reference/dot-obj-files-as-linker-input.md)

- [NETMODULE-Dateien](../../build/reference/netmodule-files-as-linker-input.md)

- [LIB-Dateien](../../build/reference/dot-lib-files-as-linker-input.md)

- [.EXP-Dateien](../../build/reference/dot-exp-files-as-linker-input.md)

- [DEF-Dateien](../../build/reference/dot-def-files-as-linker-input.md)

- [PDB-Dateien](../../build/reference/dot-pdb-files-as-linker-input.md)

- [.RES-Dateien](../../build/reference/dot-res-files-as-linker-input.md)

- [.exe-Dateien](../../build/reference/dot-exe-files-as-linker-input.md)

- [TXT-Dateien](../../build/reference/dot-txt-files-as-linker-input.md)

- [ILK-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)