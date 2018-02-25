---
title: '#include-Direktive (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#include'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, directives
- '#include directive'
- include directive (#include)
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cee268b68d9be823c6919780f8f4f25e78e1eb74
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="include-directive-cc"></a>#include-Anweisung (C/C++)
Weist den Präprozessor an, den Inhalt einer angegebenen Datei so zu behandeln, als ob dieser im Quellprogramm an demselben Punkt wie die Anweisung auftreten würde.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      #include  "path-spec"  
#include  <path-spec>  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die Definitionen von Konstanten und Makros in Includedateien einschließen und `#include`-Direktiven verwenden, um sie in beliebigen Quelldateien hinzuzufügen. Includedateien sind auch nützlich, um Deklarationen von externen Variablen und komplexe Datentypen zu integrieren. Die Typen können nur einmal in einer für diesen Zweck erstellten Includedatei definiert und benannt werden.  
  
 `path-spec` ist ein Dateiname, dem optional eine Verzeichnisangabe vorangestellt werden kann. Der Dateiname muss eine vorhandene Datei benennen. Die Syntax von `path-spec` hängt vom Betriebssystem ab, unter dem das Programm kompiliert wird.  
  
 Informationen dazu, wie Sie Assemblys in einer C++-Anwendung verweisen, die kompiliert wird ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), finden Sie unter [#using](../preprocessor/hash-using-directive-cpp.md).  
  
 Beide Syntaxformate führen dazu, dass diese Anweisung durch den gesamten Inhalt der angegebenen Includedatei ersetzt werden kann. Der Unterschied zwischen den beiden Formaten liegt in der Reihenfolge, in der der Präprozessor nach den Headerdateien sucht, wenn der Pfad unvollständig angegeben wurde. In der folgenden Tabelle wird der Unterschied zwischen den beiden Syntaxformaten gezeigt.  
  
|Syntaxformat|Aktion|  
|-----------------|------------|  
|Format mit Anführungszeichen|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> (1) im selben Verzeichnis wie die Datei mit der `#include` Anweisung.<br /><br /> (2) in den Verzeichnissen der aktuell geöffneten Includedateien Sie in umgekehrter Reihenfolge, in dem sie geöffnet wurden. Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.<br /><br /> (3) entlang des Pfads, der durch die einzelnen/i-Compileroptionen angegeben wird.<br /><br /> 4)<br /><br /> Entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben wurden.|  
|Format mit spitzer Klammer|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> (1) entlang des Pfads, der durch die einzelnen/i-Compileroptionen angegeben wird.<br /><br /> (2) beim Kompilieren in der Befehlszeile sind entlang der Pfade, die durch die INCLUDE-Umgebungsvariable angegeben.|  
  
 Der Präprozessor beendet die Suche, sobald eine Datei mit dem angegebenen Namen gefunden wird. Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen doppelten Anführungszeichen (" ") angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.  
  
 Wenn der in doppelte Anführungszeichen eingeschlossene Dateiname eine unvollständige Pfadangabe ist, sucht der Präprozessor zuerst das Verzeichnis der "übergeordneten" Datei. Eine übergeordnete Datei ist die Datei, in der die `#include`-Direktive enthalten ist. Wenn Sie beispielsweise eine Datei namens `file2` in eine Datei namens `file1` einschließen, ist `file1` die übergeordnete Datei.  
  
 Includedateien können "geschachtelt" werden, d. h. eine `#include`-Direktive kann in einer Datei angezeigt werden, die durch eine andere `#include`-Direktive benannt wurde. `file2` kann beispielsweise `file3` enthalten. In diesem Fall würde `file1` weiterhin das übergeordnete Element von `file2` sein und gleichzeitig die zweite übergeordnete Ebene von `file3`.  
  
 Wenn Includedateien geschachtelt sind und die Kompilierung von der Befehlszeile erfolgt, beginnt die Suche in den Verzeichnissen der übergeordneten Datei. Danach werden die Verzeichnisse aller Dateien der zweiten übergeordneten Ebene durchsucht. Dies bedeutet, dass die Suche relativ zum Verzeichnis beginnt, das die Quelldatei enthält, die gerade verarbeitet wird. Wenn die Datei nicht gefunden wird, wird die Suche in den durch die /I-Compileroption angegebenen Verzeichnissen fortgesetzt. Zuletzt werden die durch die INCLUDE-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.  
  
 Aus der Entwicklungsumgebung wird die INCLUDE-Umgebungsvariable ignoriert. Informationen zum Festlegen von die Verzeichnisse, die nach Includedateien durchsucht werden – dies gilt auch für die LIB-Umgebungsvariable – finden Sie unter [VC++-Verzeichnisse Eigenschaftenseite](../ide/vcpp-directories-property-page.md).  
  
 In diesem Beispiel sehen Sie, wie mithilfe der spitzen Klammern Dateien in die Suche einbezogen werden:  
  
```  
#include <stdio.h>  
```  
  
 In diesem Beispiel wird der Inhalt der Datei namens STDIO.H dem Quellprogramm hinzugefügt. Durch die spitzen Klammern werden vom Präprozessor zuerst die durch die /I-Compileroption angegebenen Verzeichnisse durchsucht und dann die durch die INCLUDE-Umgebungsvariable für STDIO.H angegebenen Verzeichnisse.  
  
 Im nächsten Beispiel sehen Sie, wie mithilfe der Anführungszeichen Dateien in die Suche einbezogen werden:  
  
```  
#include "defs.h"  
```  
  
 In diesem Beispiel wird der Inhalt der durch DEFS.H angegebenen Datei dem Quellprogramm hinzugefügt. Die doppelten Anführungszeichen bewirken, dass der Präprozessor zuerst das Verzeichnis mit der übergeordneten Quelldatei durchsucht.  
  
 Includedateien können auf bis zu 10 Ebenen geschachtelt werden. Sobald die geschachtelte `#include`-Datei verarbeitet ist, wird vom Präprozessor die einschließende Includedatei in die ursprüngliche Quelldatei eingefügt.  
  
 **Microsoft-spezifisch**  
  
 Um die Quelldateien zu finden, die einbezogen werden können, durchsucht der Präprozessor zuerst die Verzeichnisse, die durch die /I- Compileroption angegeben werden. Wenn die /I-Option nicht vorhanden ist oder Fehler auftreten, verwendet der Präprozessor die INCLUDE-Umgebungsvariable, um alle Includedateien in spitzen Klammern zu suchen. Die INCLUDE-Umgebungsvariable und die /I-Compileroption können mehrere Pfade enthalten, die durch Semikolons (;) getrennt werden. Wenn mehrere Verzeichnisse in der /I-Option oder der INCLUDE-Umgebungsvariablen enthalten sind, werden diese vom Präprozessor in der Reihenfolge durchsucht, in der sie angezeigt werden.  
  
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
  
 Für die Includedateien, die als angegeben sind `#include` "`path-spec`", beginnt mit dem Verzeichnis der übergeordneten Datei zu Verzeichnissuchen, und klicken Sie dann in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt. Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei mit der `#include`-Direktive enthält, die verarbeitet wird. Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)