---
title: Einschließlich Dateinamen in Klammern
ms.date: 11/04/2016
ms.assetid: 6a4e5411-c35e-48b8-90ef-b37ac324ed94
ms.openlocfilehash: 87de00814f58ed86ee33abdcf96dd210f418c5ba
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147580"
---
# <a name="including-bracketed-filenames"></a>Einschließlich Dateinamen in Klammern

**ANSI 3.8.2** Die Methode zum Suchen von Quelldateien, die einbezogen werden können

Der Präprozessor sucht nicht in Verzeichnissen der übergeordneten Dateien nach Dateispezifikationen, die in eckige Klammern eingeschlossen werden. Eine „übergeordnete“ Datei ist die Datei, die die [#include](../preprocessor/hash-include-directive-c-cpp.md)-Anweisung enthält. Stattdessen beginnt die Suche nach der Datei in den Verzeichnissen, die in der Compilerbefehlszeile nach "/I" angegeben werden. Wenn die /I-Option nicht vorhanden ist oder Fehler auftreten, verwendet der Präprozessor die INCLUDE-Umgebungsvariable, um alle Includedateien in spitzen Klammern zu suchen. Die INCLUDE-Umgebungsvariable kann mehrere Pfade enthalten, die durch Semikolons (**;**) voneinander getrennt sind. Wenn mehrere Verzeichnisse in der /I-Option oder der INCLUDE-Umgebungsvariablen enthalten sind, werden diese vom Präprozessor in der Reihenfolge durchsucht, in der sie angezeigt werden.

## <a name="see-also"></a>Siehe auch

[Präprozessoranweisungen](../c-language/preprocessing-directives.md)
