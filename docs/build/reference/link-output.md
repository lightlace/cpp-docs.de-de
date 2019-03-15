---
title: LINK-Ausgabe
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 183f83501d930188032ec4209623ef7cf1a30efa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807623"
---
# <a name="link-output"></a>LINK-Ausgabe

Link-Ausgabe enthält die .exe-Dateien, DLLs, Nachrichten und Zuordnungsdateien verwendet werden.

##  <a name="_core_output_files"></a> Ausgabedateien

Die Standard-Ausgabedatei von LINK ist eine .exe-Datei. Wenn die [/DLL](dll-build-a-dll.md) angegeben wird, eine DLL-Datei verknüpfen von builds. Sie können steuern, Name der Ausgabedatei mit der [Ausgabedatei (/ OUT)](out-output-file-name.md) Option.

Im inkrementellen Modus erstellt LINK eine ILK-Datei zum Speichern von Statusinformationen für später inkrementelle Builds des Programms an. Weitere Informationen über die ILK-Dateien, finden Sie unter [ILK-Dateien](dot-ilk-files-as-linker-input.md). Weitere Informationen zu inkrementellen verknüpfen, finden Sie unter den [inkrementell verknüpfen (/ INCREMENTAL)](incremental-link-incrementally.md) Option.

Wenn der LINK erstellt ein Programm, das enthält exportiert (in der Regel eine DLL), wird auch eine LIB-Datei erstellt, sofern eine .exp-Datei in den Build verwendet wurde. Sie können den Dateinamen der Importbibliothek mit steuern die [/IMPLIB](implib-name-import-library.md) Option.

Wenn die [Zuordnungsdatei generieren (/ MAP)](map-generate-mapfile.md) angegeben wurde, LINK erstellt eine Zuordnungsdatei.

Wenn die [Debuginfo generieren (/ DEBUG)](debug-generate-debug-info.md) angegeben wurde, LINK erstellt eine PDB-Datei, die Debuginformationen für das Programm enthält.

##  <a name="_core_other_output"></a> Andere Ausgabe

Bei der Eingabe `link` ohne weitere Eingaben,-LINK zeigt eine nutzungsanweisung an, die die verfügbaren Optionen zusammengefasst sind.

LINK zeigt eine Meldung Copyright- und Versionsinformationen und Befehlsdatei Eingabe gibt, es sei denn, die [Startbanner unterdrücken (/ NOLOGO)](nologo-suppress-startup-banner-linker.md) Option wird verwendet.

Sie können die [Meldungen zum Ausgabefortschritt (/ VERBOSE)](verbose-print-progress-messages.md) Option aus, um zusätzliche Details über den Build anzuzeigen.

LINK gibt Fehler- und warnungsmeldungen Nachrichten in der Form LNK*Nnnn*. Dieser Fehlerpräfix und den Bereich von Zahlen werden auch von LIB, DUMPBIN und EDITBIN verwendet.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
