---
title: Linkertoolfehler LNK1123
ms.date: 12/29/2017
f1_keywords:
- LNK1123
helpviewer_keywords:
- LNK1123
ms.openlocfilehash: 31fd634291bfb0af17348197ae8a6225ac490c89
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509903"
---
# <a name="linker-tools-error-lnk1123"></a>Linkertoolfehler LNK1123

> Fehler bei der Konvertierung in COFF: Datei ist ungültig oder beschädigt

Eingabedateien müssen das Common Object File Format(COFF)-Format haben. Besitzt eine Eingabedatei kein COFF-Format, versucht der Linker automatisch, 32-Bit-OMF-Objekte in COFF zu konvertieren, oder führt CVTRES.EXE aus, um Ressourcendateien zu konvertieren. Diese Meldung gibt an, dass der Linker die Datei nicht konvertieren konnte. Das kann auch bei der Verwendung einer inkompatiblen Version von CVTRES.EXE aus einer anderen Installation von Visual Studio, dem Windows Development Kit oder .NET Framework auftreten.

> [!NOTE]
> Wenn Sie eine frühere Version von Visual Studio ausführen, wird die automatische Konvertierung möglicherweise nicht unterstützt.

## <a name="to-fix-the-problem"></a>So beheben Sie dieses Problem

- Übernehmen Sie alle Servicepacks und Updates für Ihre Version von Visual Studio. Dies ist besonders wichtig für Visual Studio 2010.

- Versuchen Sie das Erstellen mit deaktivierten inkrementellen Verknüpfen. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. Erweitern Sie im Dialogfeld Eigenschaften **Seiten** die Option **Konfigurations Eigenschaften**, **Linker**. Ändern Sie den Wert von **inkrementelles Verknüpfen aktivieren** in **Nein**.

- Überprüfen Sie, ob die Version von CVTRES.EXE, die zuerst in Ihrer PATH-Umgebungsvariable gefunden wird, der Version der in Ihrem Projekt verwendeten Buildtoos oder der Version des Plattformtoolsets entspricht.

- Versuchen Sie, die Option „Manifest einbetten“ zu deaktivieren. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. Erweitern Sie im Dialogfeld Eigenschaften **Seiten** die Option **Konfigurations Eigenschaften**, **Manifest-Tool**, **Eingabe und Ausgabe**. Ändern Sie den Wert des **Einbettungs Manifests** in **Nein**.

- Stellen Sie sicher, dass der Dateityp gültig ist. Stellen Sie zum Beispiel sicher, dass ein OMF-Objekt ein 32-Bit-Objekt und kein 16-Bit-Objekt ist. Weitere Informationen finden Sie unter [. OBJ-Dateien als Eingabe](../../build/reference/dot-obj-files-as-linker-input.md) -und [PE-Format](/windows/win32/Debug/pe-format)für den Linker.

- Stellen Sie sicher, dass die Datei nicht beschädigt ist. Erstellen Sie neu, falls erforderlich.

## <a name="see-also"></a>Siehe auch

[.obj-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md)<br/>
[EDITBIN-Referenz](../../build/reference/editbin-reference.md)<br/>
[DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md)
