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
ms.openlocfilehash: da68f71d2a3830cdd86870d8ef072c3fb04933db
ms.sourcegitcommit: 45835842604602a011813d0cd70abc5df91b89ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "50750404"
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

Die *Path-Spec* ist der Name einer Datei, die optional eine Verzeichnisangabe vorangestellt werden kann. Der Dateiname muss eine vorhandene Datei benennen. Die Syntax der *Path-Spec* hängt von dem Betriebssystem, unter dem das Programm kompiliert wird.

Informationen dazu, wie Sie Assemblys in einer C++-Anwendung verweisen, die kompiliert wird ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), finden Sie unter [#using](../preprocessor/hash-using-directive-cpp.md).

Beide Syntaxformate führen dazu, dass diese Anweisung durch den gesamten Inhalt der angegebenen Includedatei ersetzt werden kann. Der Unterschied zwischen den beiden Formaten liegt in der Reihenfolge, in der der Präprozessor nach den Headerdateien sucht, wenn der Pfad unvollständig angegeben wurde. In der folgenden Tabelle wird der Unterschied zwischen den beiden Syntaxformaten gezeigt.

|Syntaxformat|Aktion|
|---|------------|
|Format mit Anführungszeichen|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br/><br/> (1) im selben Verzeichnis wie die Datei mit den **#include** Anweisung.<br/><br/> (2) in den Verzeichnissen der aktuell geöffneten Includedateien Sie in umgekehrter Reihenfolge, in dem sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.<br/><br/> (3) entlang des Pfads, der von jeder Instanz angegeben wird **/i** -Compileroption.<br/><br/> (4) entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben werden.|
|Format mit spitzer Klammer|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br/><br/> (1) entlang des Pfads, der von jeder Instanz angegeben wird **/i** -Compileroption.<br/><br/> (2) bei der Kompilierung in der Befehlszeile angegeben werden entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben werden.|

Der Präprozessor beendet die Suche, sobald eine Datei mit dem angegebenen Namen gefunden wird. Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen doppelten Anführungszeichen einschließen (**""**), der Präprozessor sucht nur diese Pfadangabe und ignoriert die Standardverzeichnisse.

Wenn der in doppelte Anführungszeichen eingeschlossene Dateiname eine unvollständige Pfadangabe ist, sucht der Präprozessor zuerst das Verzeichnis der "übergeordneten" Datei. Eine übergeordnete Datei ist die Datei mit den **#include** Richtlinie. Angenommen, Sie eine Datei mit dem Namen aufnehmen *Datei2* in einer Datei namens *"file1"*, *"file1"* die übergeordnete Datei.

Includedateien Sie "geschachtelt werden können"; d. h. eine **#include** Richtlinie darf in einer Datei mit dem Namen von einem anderen **#include** Richtlinie. Z. B. *Datei2* kann umfassen *Datei3*. In diesem Fall *"file1"* wäre immer noch das übergeordnete Element des *Datei2*, aber es wäre die zweite "übergeordnete" der *Datei3*.

Wenn Includedateien geschachtelt sind und die Kompilierung von der Befehlszeile erfolgt, beginnt die Suche in den Verzeichnissen der übergeordneten Datei. Danach werden die Verzeichnisse aller Dateien der zweiten übergeordneten Ebene durchsucht. Dies bedeutet, dass die Suche relativ zum Verzeichnis beginnt, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn die Datei nicht gefunden wird, wird die Suche in Verzeichnissen mit den vom angegebenen fortgesetzt der [/i (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md) -Compileroption. Zuletzt werden die durch die INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.

In der Visual Studio-Entwicklungsumgebung wird die INCLUDE-Umgebungsvariable ignoriert. Informationen zum Festlegen der Verzeichnisse, die nach Includedateien durchsucht werden – dies gilt auch für die LIB-Umgebungsvariable – finden Sie unter [VC++ Directories Property Page](../ide/vcpp-directories-property-page.md).

In diesem Beispiel sehen Sie, wie mithilfe der spitzen Klammern Dateien in die Suche einbezogen werden:

```
#include <stdio.h>
```

In diesem Beispiel wird der Inhalt der Datei namens STDIO.H dem Quellprogramm hinzugefügt. Die spitzen Klammern vom Präprozessor zuerst die Verzeichnisse zu suchen, die durch die INCLUDE-Umgebungsvariable für STDIO angegeben sind. H, die mit den vom angegebenen Verzeichnisse durchsucht die **/i** -Compileroption.

Im nächsten Beispiel sehen Sie, wie mithilfe der Anführungszeichen Dateien in die Suche einbezogen werden:

```
#include "defs.h"
```

In diesem Beispiel wird der Inhalt der durch DEFS.H angegebenen Datei dem Quellprogramm hinzugefügt. Die doppelten Anführungszeichen bewirken, dass der Präprozessor zuerst das Verzeichnis mit der übergeordneten Quelldatei durchsucht.

Includedateien können auf bis zu 10 Ebenen geschachtelt werden. Wenn die geschachtelte **#include** wird verarbeitet, weiterhin der Präprozessor die einschließende Includedatei in die ursprüngliche Quelldatei eingefügt.

**Microsoft-spezifisch**

Um einbezogen werden können Quelldateien zu finden, sucht der Präprozessor zuerst die Verzeichnisse, die vom angegebenen die **/i** -Compileroption. Wenn die **/i** Option ist nicht vorhanden, oder ein Fehler auftritt, verwendet des Präprozessors die INCLUDE-Umgebungsvariable um alle Includedateien in spitzen Klammern zu finden. INCLUDE-Umgebungsvariable und **/i** Compileroption können mehrere Pfade, die durch Semikolons getrennt enthalten (**;**). Wenn mehr als ein Verzeichnis angezeigt, als Teil wird der **/i** option oder in der INCLUDE-Umgebungsvariable, die Präprozessor sucht sie in der Reihenfolge, in der sie angezeigt werden.

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

Für die Includedateien, die als angegeben sind `#include "path-spec"`, Suche, in dem Verzeichnis der übergeordneten Datei gestartet, und klicken Sie dann in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Das beginnt die Suche relativ zum Verzeichnis, das die Quelldatei enthält, enthält die **#include** Richtlinie, die verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)<br/>
[/ I (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md)<br/>
