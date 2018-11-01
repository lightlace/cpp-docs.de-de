---
title: '##include-Direktive (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
ms.openlocfilehash: 3cf595fd8f519706f43ad70c4cdddf0297c8149e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492533"
---
# <a name="include-directive-cc"></a>#include-Anweisung (C/C++)
Weist den Präprozessor an, den Inhalt einer angegebenen Datei so zu behandeln, als ob dieser im Quellprogramm an demselben Punkt wie die Anweisung auftreten würde.

## <a name="syntax"></a>Syntax

```
#include  "path-spec"
#include  <path-spec>
```

## <a name="remarks"></a>Hinweise

Sie können Definitionen von Konstanten und Makros in Includedateien zu organisieren und dann **#include** Anweisungen, um sie in beliebigen Quelldateien hinzuzufügen. Includedateien sind auch nützlich, um Deklarationen von externen Variablen und komplexe Datentypen zu integrieren. Die Typen können nur einmal in einer für diesen Zweck erstellten Includedatei definiert und benannt werden.

`path-spec` ist ein Dateiname, dem optional eine Verzeichnisangabe vorangestellt werden kann. Der Dateiname muss eine vorhandene Datei benennen. Die Syntax von `path-spec` hängt vom Betriebssystem ab, unter dem das Programm kompiliert wird.

Informationen dazu, wie Sie Assemblys in einer C++-Anwendung verweisen, die kompiliert wird ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), finden Sie unter [#using](../preprocessor/hash-using-directive-cpp.md).

Beide Syntaxformate führen dazu, dass diese Anweisung durch den gesamten Inhalt der angegebenen Includedatei ersetzt werden kann. Der Unterschied zwischen den beiden Formaten liegt in der Reihenfolge, in der der Präprozessor nach den Headerdateien sucht, wenn der Pfad unvollständig angegeben wurde. In der folgenden Tabelle wird der Unterschied zwischen den beiden Syntaxformaten gezeigt.

|Syntaxformat|Aktion|
|-----------------|------------|
|Format mit Anführungszeichen|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> (1) im selben Verzeichnis wie die Datei mit den **#include** Anweisung.<br /><br /> (2) in den Verzeichnissen der aktuell geöffneten Includedateien Sie in umgekehrter Reihenfolge, in dem sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.<br /><br /> (3) entlang des Pfads, der von jeder Instanz angegeben wird `/I` -Compileroption.<br /><br /> 4)<br /><br /> Entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben wurden.|
|Format mit spitzer Klammer|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> (1) entlang des Pfads, der von jeder Instanz angegeben wird `/I` -Compileroption.<br /><br /> (2) bei der Kompilierung in der Befehlszeile angegeben werden entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben werden.|

Der Präprozessor beendet die Suche, sobald eine Datei mit dem angegebenen Namen gefunden wird. Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen doppelten Anführungszeichen (" ") angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.

Wenn der in doppelte Anführungszeichen eingeschlossene Dateiname eine unvollständige Pfadangabe ist, sucht der Präprozessor zuerst das Verzeichnis der "übergeordneten" Datei. Eine übergeordnete Datei ist die Datei mit den **#include** Richtlinie. Wenn Sie beispielsweise eine Datei namens `file2` in eine Datei namens `file1` einschließen, ist `file1` die übergeordnete Datei.

Includedateien Sie "geschachtelt werden können"; d. h. eine **#include** Richtlinie darf in einer Datei mit dem Namen von einem anderen **#include** Richtlinie. `file2` kann beispielsweise `file3` enthalten. In diesem Fall würde `file1` weiterhin das übergeordnete Element von `file2` sein und gleichzeitig die zweite übergeordnete Ebene von `file3`.

Wenn Includedateien geschachtelt sind und die Kompilierung von der Befehlszeile erfolgt, beginnt die Suche in den Verzeichnissen der übergeordneten Datei. Danach werden die Verzeichnisse aller Dateien der zweiten übergeordneten Ebene durchsucht. Dies bedeutet, dass die Suche relativ zum Verzeichnis beginnt, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn die Datei nicht gefunden wird, wird die Suche in Verzeichnissen mit den vom angegebenen fortgesetzt der `/I` -Compileroption. Zuletzt werden die durch die INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.

Aus der Entwicklungsumgebung wird die INCLUDE-Umgebungsvariable ignoriert. Informationen zum Festlegen der Verzeichnisse, die nach Includedateien durchsucht werden – dies gilt auch für die LIB-Umgebungsvariable – finden Sie unter [VC++ Directories Property Page](../ide/vcpp-directories-property-page.md).

In diesem Beispiel sehen Sie, wie mithilfe der spitzen Klammern Dateien in die Suche einbezogen werden:

```
#include <stdio.h>
```

In diesem Beispiel wird der Inhalt der Datei namens STDIO.H dem Quellprogramm hinzugefügt. Die spitzen Klammern vom Präprozessor zuerst die Verzeichnisse zu suchen, die durch die INCLUDE-Umgebungsvariable für STDIO angegeben sind. H, die mit den vom angegebenen Verzeichnisse durchsucht die `/I` -Compileroption.

Im nächsten Beispiel sehen Sie, wie mithilfe der Anführungszeichen Dateien in die Suche einbezogen werden:

```
#include "defs.h"
```

In diesem Beispiel wird der Inhalt der durch DEFS.H angegebenen Datei dem Quellprogramm hinzugefügt. Die doppelten Anführungszeichen bewirken, dass der Präprozessor zuerst das Verzeichnis mit der übergeordneten Quelldatei durchsucht.

Includedateien können auf bis zu 10 Ebenen geschachtelt werden. Wenn die geschachtelte **#include** wird verarbeitet, weiterhin der Präprozessor die einschließende Includedatei in die ursprüngliche Quelldatei eingefügt.

**Microsoft-spezifisch**

Um einbezogen werden können Quelldateien zu finden, sucht der Präprozessor zuerst die Verzeichnisse, die vom angegebenen die `/I` -Compileroption. Wenn die `/I` Option ist nicht vorhanden, oder ein Fehler auftritt, verwendet des Präprozessors die INCLUDE-Umgebungsvariable um alle Includedateien in spitzen Klammern zu finden. INCLUDE-Umgebungsvariable und `/I` Compileroption können mehrere Pfade, die durch Semikolons (;) getrennt enthalten. Wenn mehr als ein Verzeichnis angezeigt, als Teil wird der `/I` option oder in der INCLUDE-Umgebungsvariable, die Präprozessor sucht sie in der Reihenfolge, in der sie angezeigt werden.

Mit dem Befehl

```
CL /ID:\MSVC\INCLUDE MYPROG.C
```

beispielsweise wird der Präprozessor veranlasst, das Verzeichnis D:\MSVC\INCLUDE\ nach Includedateien wie STDIO.H. zu durchsuchen. Die Befehle

```
SET INCLUDE=D:\MSVC\INCLUDE
CL MYPROG.C
```

haben dieselbe Wirkung. Wenn es bei beiden Suchvorgängen zu Fehlern kommt, tritt ein schwerwiegender Compilerfehler auf.

Wenn der Dateiname für eine Includedatei mit einem Pfad, der einen Doppelpunkt enthält (z. B. F:\MSVC\SPECIAL\INCL\TEST.H) vollständig angegeben wurde, folgt der Präprozessor dem Pfad.

Für die Includedateien, die als angegeben sind `#include` "`path-spec`", Suche, in dem Verzeichnis der übergeordneten Datei gestartet, und klicken Sie dann in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Das beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, enthält die **#include** Richtlinie, die verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)