---
title: Zusätzliche MSVC-Buildtools
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 53c7c2f8c162cd851b4612e75ba14b019d9cbd63
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177294"
---
# <a name="additional-msvc-build-tools"></a>Zusätzliche MSVC-Buildtools

Visual Studio bietet die folgenden Befehlszeilen-Hilfsprogramme zum Anzeigen oder Bearbeiten der Buildausgabe:

- [Lib. EXE](lib-reference.md) wird verwendet, um eine Bibliothek von COFF-Objektdateien (Common Object File Format) zu erstellen und zu verwalten. Sie kann auch zum Erstellen von Export Dateien und Importieren von Bibliotheken verwendet werden, um auf exportierte Definitionen zu verweisen.

- [EDITBIN. EXE](editbin-reference.md) wird verwendet, um COFF-Binärdateien zu ändern.

- [DUMPBIN. EXE](dumpbin-reference.md) zeigt Informationen (z. b. eine Symboltabelle) zu COFF-Binärdateien an.

- [NMAKE](nmake-reference.md) liest Makefiles und führt Sie aus.

- [ERRLOOK](value-edit-control.md), das Hilfsprogramm für die Fehlersuche, ruft eine Systemfehlermeldung oder Modul Fehlermeldung auf Grundlage des eingegebenen Werts ab.

- [XDCMake](xdcmake-reference.md). Ein Tool für die Verarbeitung von Quell Code Dateien, die Dokumentations Kommentare enthalten, die mit XML-Tags markiert sind.

- [BSCMAKE. EXE](bscmake-reference.md) (nur aus Gründen der Abwärtskompatibilität bereitgestellt) erstellt eine Browseinformationsdatei (. BSC), die Informationen zu den Symbolen (Klassen, Funktionen, Daten, Makros und Typen) in Ihrem Programm enthält. Diese Informationen werden in den Such Fenstern innerhalb der Entwicklungsumgebung angezeigt. (Eine BSC-Datei kann auch in der Entwicklungsumgebung erstellt werden.)

Der Windows SDK verfügt auch über mehrere Buildtools, einschließlich [RC. EXE](/windows/win32/menurc/resource-compiler), das der C++ Compiler aufruft, um systemeigene Windows-Ressourcen wie Dialogfelder, Eigenschaften Seiten, Bitmaps, Zeichen folgen Tabellen usw. zu kompilieren.

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)<br/>
[Ergänzte Namen](decorated-names.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
