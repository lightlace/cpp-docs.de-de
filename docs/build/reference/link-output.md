---
title: LINK-Ausgabe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ca32769d7797446dbb0766c41867da1554b037f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706211"
---
# <a name="link-output"></a>LINK-Ausgabe

Link-Ausgabe enthält die .exe-Dateien, DLLs, Nachrichten und Zuordnungsdateien verwendet werden.

##  <a name="_core_output_files"></a> Ausgabedateien

Die Standard-Ausgabedatei von LINK ist eine .exe-Datei. Wenn die [/DLL](../../build/reference/dll-build-a-dll.md) angegeben wird, eine DLL-Datei verknüpfen von builds. Sie können steuern, Name der Ausgabedatei mit der [Ausgabedatei (/ OUT)](../../build/reference/out-output-file-name.md) Option.

Im inkrementellen Modus erstellt LINK eine ILK-Datei zum Speichern von Statusinformationen für später inkrementelle Builds des Programms an. Weitere Informationen über die ILK-Dateien, finden Sie unter [ILK-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md). Weitere Informationen zu inkrementellen verknüpfen, finden Sie unter den [inkrementell verknüpfen (/ INCREMENTAL)](../../build/reference/incremental-link-incrementally.md) Option.

Wenn der LINK erstellt ein Programm, das enthält exportiert (in der Regel eine DLL), wird auch eine LIB-Datei erstellt, sofern eine .exp-Datei in den Build verwendet wurde. Sie können den Dateinamen der Importbibliothek mit steuern die [/IMPLIB](../../build/reference/implib-name-import-library.md) Option.

Wenn die [Zuordnungsdatei generieren (/ MAP)](../../build/reference/map-generate-mapfile.md) angegeben wurde, LINK erstellt eine Zuordnungsdatei.

Wenn die [Debuginfo generieren (/ DEBUG)](../../build/reference/debug-generate-debug-info.md) angegeben wurde, LINK erstellt eine PDB-Datei, die Debuginformationen für das Programm enthält.

##  <a name="_core_other_output"></a> Andere Ausgabe

Bei der Eingabe `link` ohne weitere Eingaben,-LINK zeigt eine nutzungsanweisung an, die die verfügbaren Optionen zusammengefasst sind.

LINK zeigt eine Meldung Copyright- und Versionsinformationen und Befehlsdatei Eingabe gibt, es sei denn, die [Startbanner unterdrücken (/ NOLOGO)](../../build/reference/nologo-suppress-startup-banner-linker.md) Option wird verwendet.

Sie können die [Meldungen zum Ausgabefortschritt (/ VERBOSE)](../../build/reference/verbose-print-progress-messages.md) Option aus, um zusätzliche Details über den Build anzuzeigen.

LINK gibt Fehler- und warnungsmeldungen Nachrichten in der Form LNK*Nnnn*. Dieser Fehlerpräfix und den Bereich von Zahlen werden auch von LIB, DUMPBIN und EDITBIN verwendet.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)