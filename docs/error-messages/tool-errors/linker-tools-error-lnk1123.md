---
title: Linkertoolfehler LNK1123
ms.date: 12/29/2017
f1_keywords:
- LNK1123
helpviewer_keywords:
- LNK1123
ms.openlocfilehash: b67a2a4ddad13988967b7cc7d827862a2a6fe933
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456419"
---
# <a name="linker-tools-error-lnk1123"></a>Linkertoolfehler LNK1123

> Fehler bei der Konvertierung in COFF: Datei ist ungültig oder beschädigt

Eingabedateien müssen das Common Object File Format(COFF)-Format haben. Besitzt eine Eingabedatei kein COFF-Format, versucht der Linker automatisch, 32-Bit-OMF-Objekte in COFF zu konvertieren, oder führt CVTRES.EXE aus, um Ressourcendateien zu konvertieren. Diese Meldung gibt an, dass der Linker die Datei nicht konvertieren konnte. Das kann auch bei der Verwendung einer inkompatiblen Version von CVTRES.EXE aus einer anderen Installation von Visual Studio, dem Windows Development Kit oder .NET Framework auftreten.

> [!NOTE]
> Wenn Sie eine frühere Version von Visual Studio ausführen, wird die automatische Konvertierung möglicherweise nicht unterstützt.

## <a name="to-fix-the-problem"></a>So beheben Sie dieses Problem

- Übernehmen Sie alle Servicepacks und Updates für Ihre Version von Visual Studio. Dies ist besonders wichtig für Visual Studio 2010.

- Versuchen Sie das Erstellen mit deaktivierten inkrementellen Verknüpfen. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. In der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften**, **Linker**. Ändern Sie den Wert der **inkrementelles Verknüpfen aktivieren** zu **keine**.

- Überprüfen Sie, ob die Version von CVTRES.EXE, die zuerst in Ihrer PATH-Umgebungsvariable gefunden wird, der Version der in Ihrem Projekt verwendeten Buildtoos oder der Version des Plattformtoolsets entspricht.

- Versuchen Sie, die Option „Manifest einbetten“ zu deaktivieren. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. In der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften**, **Manifesttool**, **ein- und Ausgabe**. Ändern Sie den Wert der **Manifest einbetten** zu **keine**.

- Stellen Sie sicher, dass der Dateityp gültig ist. Stellen Sie zum Beispiel sicher, dass ein OMF-Objekt ein 32-Bit-Objekt und kein 16-Bit-Objekt ist. Weitere Informationen finden Sie unter [. OBJ-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md) und [PE-Format](/windows/desktop/Debug/pe-format).

- Stellen Sie sicher, dass die Datei nicht beschädigt ist. Erstellen Sie neu, falls erforderlich.

## <a name="see-also"></a>Siehe auch

[.obj-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md)<br/>
[EDITBIN-Referenz](../../build/reference/editbin-reference.md)<br/>
[DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md)
