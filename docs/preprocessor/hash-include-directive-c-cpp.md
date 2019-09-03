---
title: '##include-Anweisung (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#include'
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
ms.openlocfilehash: 0792f522427e5658de992969745878894fbd454d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220249"
---
# <a name="include-directive-cc"></a>#include-Direktive (C++C/)

Weist den Präprozessor an, den Inhalt einer angegebenen Datei so zu behandeln, als ob dieser im Quellprogramm an demselben Punkt wie die Direktive auftreten würde.

## <a name="syntax"></a>Syntax

> **#include** "*path-spec*" \
> **#include** \< *Pfadspezifikation*>

## <a name="remarks"></a>Hinweise

Sie können Konstante und Makro Definitionen in Includedateien organisieren und dann **#include** -Direktiven verwenden, um Sie zu beliebigen Quelldateien hinzuzufügen. Includedateien sind auch nützlich, um Deklarationen von externen Variablen und komplexe Datentypen zu integrieren. Die Typen können nur einmal in einer für diesen Zweck erstellten Includedatei definiert und benannt werden.

" *Path-spec* " ist ein Dateiname, dem optional eine Verzeichnis Spezifikation vorangestellt werden kann. Der Dateiname muss eine vorhandene Datei benennen. Die Syntax der *Pfadspezifikation* hängt von dem Betriebssystem ab, unter dem das Programm kompiliert wird.

Informationen zum Referenzieren von Assemblys in C++ einer-Anwendung, die mithilfe von [/CLR](../build/reference/clr-common-language-runtime-compilation.md)kompiliert wurde, finden Sie unter [#using](../preprocessor/hash-using-directive-cpp.md).

Beide Syntaxformate führen dazu, dass diese Direktive durch den gesamten Inhalt der angegebenen Includedatei ersetzt werden kann. Der Unterschied zwischen den beiden Formaten liegt in der Reihenfolge, in der der Präprozessor nach den Headerdateien sucht, wenn der Pfad unvollständig angegeben wurde. In der folgenden Tabelle wird der Unterschied zwischen den beiden Syntaxformaten gezeigt.

|Syntaxformat|Aktion|
|---|------------|
|Format mit Anführungszeichen|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br/><br/> 1) im gleichen Verzeichnis wie die Datei, die die **#include** -Anweisung enthält.<br/><br/> 2) in den Verzeichnissen der aktuell geöffneten Includedateien in umgekehrter Reihenfolge, in der Sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.<br/><br/> 3) entlang des Pfads, der durch jede **/I** -Compileroption angegeben wird.<br/><br/> 4) entlang der Pfade, die durch die include-Umgebungsvariable angegeben werden.|
|Format mit spitzer Klammer|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br/><br/> 1) entlang des Pfads, der durch jede **/I** -Compileroption angegeben wird.<br/><br/> 2) beim Kompilieren in der Befehlszeile entlang der Pfade, die durch die include-Umgebungsvariable angegeben werden.|

Der Präprozessor beendet die Suche, sobald eine Datei mit dem angegebenen Namen gefunden wird. Wenn Sie eine komplette, eindeutige Pfadangabe für die Includedatei zwischen doppelten Anführungszeichen (`" "`) einschließen, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standard Verzeichnisse.

Wenn der in doppelte Anführungszeichen eingeschlossene Dateiname eine unvollständige Pfadangabe ist, sucht der Präprozessor zuerst das Verzeichnis der "übergeordneten" Datei. Eine übergeordnete Datei ist die Datei, die die **#include** -Direktive enthält. Wenn Sie z. b. eine Datei mit dem Namen *file2* in eine Datei mit dem Namen *file1*einschließen, ist *file1* die übergeordnete Datei.

Includedateien können "eingebettet" sein: Eine **#include** -Direktive kann in einer Datei angezeigt werden, die von einer anderen **#include** -Direktive benannt wird. Beispielsweise kann *file2* *datei3*enthalten. In diesem Fall wäre *file1* immer noch das übergeordnete Element von *file2*, aber es wäre das "übergeordnete übergeordnete Element" von *datei3*.

Wenn Includedateien eingebettet sind und die Kompilierung in der Befehlszeile erfolgt, beginnt die Verzeichnis Suche in den Verzeichnissen der übergeordneten Datei. Anschließend werden die Verzeichnisse aller Dateien der zweiten übergeordneten Ebene durchlaufen. Dies bedeutet, dass die Suche relativ zum Verzeichnis beginnt, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn die Datei nicht gefunden wird, wird die Suche in Verzeichnisse verschoben, die durch die Compileroption [/I (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md) angegeben werden. Zuletzt werden die durch die INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.

In der Visual Studio-Entwicklungsumgebung wird die include-Umgebungsvariable ignoriert. Informationen zum Festlegen der Verzeichnisse, die nach Includedateien und Bibliotheksdateien durchsucht werden, finden Sie unter [VC + +-Verzeichnisse (Eigenschaften Seite](../build/reference/vcpp-directories-property-page.md)).

In diesem Beispiel sehen Sie, wie mithilfe der spitzen Klammern Dateien in die Suche einbezogen werden:

```C
#include <stdio.h>
```

In diesem Beispiel wird der Inhalt der Datei namens STDIO.H dem Quellprogramm hinzugefügt. Die spitzen Klammern bewirken, dass der Präprozessor die Verzeichnisse durchsucht, die durch die include-Umgebungsvariable für stdio angegeben werden. H nach dem Durchsuchen von Verzeichnissen, die durch die **/I** -Compileroption angegeben werden.

Im nächsten Beispiel sehen Sie, wie mithilfe der Anführungszeichen Dateien in die Suche einbezogen werden:

```C
#include "defs.h"
```

In diesem Beispiel wird der Inhalt der durch DEFS.H angegebenen Datei dem Quellprogramm hinzugefügt. Die doppelten Anführungszeichen bewirken, dass der Präprozessor zuerst das Verzeichnis mit der übergeordneten Quelldatei durchsucht.

Includedateien können auf bis zu 10 Ebenen geschachtelt werden. Wenn die #include der verarbeitet wird, fügt der Präprozessor weiterhin die einschließende Includedatei in die ursprüngliche Quelldatei ein.

**Microsoft-spezifisch**

Um inkludierbare Quelldateien zu suchen, durchsucht der Präprozessor zuerst die Verzeichnisse, die von der **/I** -Compileroption angegeben werden. Wenn die **/I** -Option nicht vorhanden ist, oder wenn Sie fehlschlägt, verwendet der Präprozessor die include-Umgebungsvariable, um beliebige Includedateien in spitzen Klammern zu suchen. Die include-Umgebungsvariable und die **/I** -Compileroption können mehrere Pfade enthalten, die durch Semikolons ( **;** ) getrennt sind. Wenn mehr als ein Verzeichnis als Teil der **/I** -Option oder innerhalb der INCLUDE-Umgebungsvariablen angezeigt wird, sucht der Präprozessor Sie in der Reihenfolge, in der Sie angezeigt werden.

Mit dem Befehl

```cmd
CL /ID:\MSVC\INCLUDE MYPROG.C
```

beispielsweise wird der Präprozessor veranlasst, das Verzeichnis D:\MSVC\INCLUDE\ nach Includedateien wie STDIO.H. zu durchsuchen. Die Befehle

```cmd
SET INCLUDE=D:\MSVC\INCLUDE
CL MYPROG.C
```

haben dieselbe Wirkung. Wenn es bei beiden Suchvorgängen zu Fehlern kommt, tritt ein schwerwiegender Compilerfehler auf.

Wenn der Dateiname für eine Includedatei mit einem Pfad, der einen Doppelpunkt enthält (z. B. F:\MSVC\SPECIAL\INCL\TEST.H) vollständig angegeben wurde, folgt der Präprozessor dem Pfad.

Bei Includedateien, die als `#include "path-spec"`angegeben werden, beginnt die Verzeichnis Suche mit dem Verzeichnis der übergeordneten Datei und durchläuft dann die Verzeichnisse aller Dateien mit zwei übergeordneten Dateien. Das heißt, das Suchen beginnt in Relation zum Verzeichnis, das die Quelldatei enthält, die die **#include** Direktive enthält, die verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)\
[/I (weitere Includeverzeichnisse)](../build/reference/i-additional-include-directories.md)
