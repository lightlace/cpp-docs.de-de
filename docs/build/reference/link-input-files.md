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
ms.openlocfilehash: 48ad9423ae35c22a97a873fe6a2a0479c12ab33b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291508"
---
# <a name="link-input-files"></a>LINK-Eingabedateien

Sie bieten den Linker Dateien, die Objekte, Import und standard-Bibliotheken, Ressourcen, Moduldefinitionen und Eingabe-Befehl enthalten. LINK verwendet Dateierweiterungen keine Annahmen zum Inhalt einer Datei. Stattdessen untersucht LINK jede Eingabedatei, um festzustellen, welche Art von Datei vorliegt.

Objektdateien in der Befehlszeile sind in der Reihenfolge verarbeitet, die sie in der Befehlszeile angezeigt werden. Bibliotheken werden in der Reihenfolge der Befehlszeile, mit der folgenden Einschränkung durchsucht: Symbole, die nicht aufgelöste beim Importieren einer Objektdatei aus einer Bibliothek in dieser Bibliothek zuerst gesucht, und klicken Sie dann die folgenden Bibliotheken über die Befehlszeile und [DEFAULTLIB (Angeben von Standard-Bibliothek)](defaultlib-specify-default-library.md) Anweisungen, und klicken Sie dann auf Bibliotheken am Anfang der Befehlszeile aus.

> [!NOTE]
>  LINK akzeptiert eine durch Semikolons (oder jedes andere Zeichen) nicht mehr als Anfang eines Kommentars in Antwortdateien und ordnen Sie Dateien an. Semikolons sind nur als Anfang eines Kommentars in Moduldefinitionsdateien (.def) erkannt.

LINK wird die folgenden Typen von Eingabedateien verwendet:

- [OBJ-Dateien](dot-obj-files-as-linker-input.md)

- [NETMODULE-Dateien](netmodule-files-as-linker-input.md)

- [LIB-Dateien](dot-lib-files-as-linker-input.md)

- [.EXP-Dateien](dot-exp-files-as-linker-input.md)

- [DEF-Dateien](dot-def-files-as-linker-input.md)

- [PDB-Dateien](dot-pdb-files-as-linker-input.md)

- [.RES-Dateien](dot-res-files-as-linker-input.md)

- [.exe-Dateien](dot-exe-files-as-linker-input.md)

- [TXT-Dateien](dot-txt-files-as-linker-input.md)

- [ILK-Dateien](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
