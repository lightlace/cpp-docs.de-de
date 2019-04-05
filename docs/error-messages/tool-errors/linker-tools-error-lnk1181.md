---
title: Linkertoolfehler LNK1181
ms.date: 08/22/2018
f1_keywords:
- LNK1181
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
ms.openlocfilehash: 657e78ece2ce4039eb8dc8561abd455c60aaff75
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59035071"
---
# <a name="linker-tools-error-lnk1181"></a>Linkertoolfehler LNK1181

Die Eingabedatei 'Dateiname' kann nicht geöffnet werden.

Der Linker wurde nicht gefunden. `filename` , da er nicht vorhanden oder der Pfad wurde nicht gefunden.

Einige häufige Ursachen für Fehler LNK1181 gehören:

- `filename` verwiesen wird, da eine zusätzliche Abhängigkeit von der Linker-Befehlszeile, aber die Datei nicht vorhanden ist.

- Ein **/LIBPATH** Anweisung, der angibt, das Verzeichnis mit `filename` ist nicht vorhanden.

Um die oben genannten Probleme zu beheben, stellen Sie sicher, dass alle Dateien, die in der Linkerzeile verwiesen wird, auf dem System vorhanden sind.  Stellen Sie außerdem sicher, es gibt eine **/LIBPATH** -Anweisung für jedes Verzeichnis, das eine Linker-abhängige Datei enthält.

Weitere Informationen finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md).

Eine weitere mögliche Ursache für LNK1181 ist, dass ein langer Dateiname mit eingebetteten Leerzeichen nicht in Anführungszeichen eingeschlossen wurde.  In diesem Fall der Linker erkennt nur einen Dateinamen bis zum ersten Leerzeichen, und dann annehmen eine Dateierweiterung aus. obj.  Die Lösung für dieses Problem besteht darin, schließen Sie den langen Dateinamen (Name, Pfad und Dateiname) in Anführungszeichen ein.

Beim Kompilieren mit der [/p (Vorverarbeitung in eine Datei)](../../build/reference/p-preprocess-to-a-file.md) Option kann in LNK1181 führen, da diese Option die Erstellung von OBJ-Dateien unterdrückt.

## <a name="see-also"></a>Siehe auch

[/LIBPATH (Libpath-Pfad hinzufügen)](../../build/reference/libpath-additional-libpath.md)