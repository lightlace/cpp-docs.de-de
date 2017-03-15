---
title: "#include-Direktive (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "#include"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#include-Direktive"
  - "include-Direktive (#include)"
  - "Präprozessor, Direktiven"
ms.assetid: 17067dc0-8db1-4f2d-b43e-ec12ecf83238
caps.latest.revision: 15
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# #include-Direktive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist den Präprozessor an, den Inhalt einer angegebenen Datei so zu behandeln, als ob dieser im Quellprogramm an demselben Punkt wie die Direktive auftreten würde.  
  
## Syntax  
  
```  
  
      #include  "path-spec"  
#include  <path-spec>  
```  
  
## Hinweise  
 Sie können die Definitionen von Konstanten und Makros in Includedateien einschließen und `#include`\-Direktiven verwenden, um sie in beliebigen Quelldateien hinzuzufügen.  Includedateien sind auch nützlich, um Deklarationen von externen Variablen und komplexe Datentypen zu integrieren.  Die Typen können nur einmal in einer für diesen Zweck erstellten Includedatei definiert und benannt werden.  
  
 `path-spec` ist ein Dateiname, dem optional eine Verzeichnisangabe vorangestellt werden kann.  Der Dateiname muss eine vorhandene Datei benennen.  Die Syntax von `path-spec` hängt vom Betriebssystem ab, unter dem das Programm kompiliert wird.  
  
 Informationen zum Verweisen auf Assemblys in einer C\+\+\-Anwendung, die mit [\/clr](../build/reference/clr-common-language-runtime-compilation.md) kompiliert wurde, erhalten Sie unter [\#using](../preprocessor/hash-using-directive-cpp.md).  
  
 Beide Syntaxformate führen dazu, dass diese Direktive durch den gesamten Inhalt der angegebenen Includedatei ersetzt werden kann.  Der Unterschied zwischen den beiden Formaten liegt in der Reihenfolge, in der der Präprozessor nach den Headerdateien sucht, wenn der Pfad unvollständig angegeben wurde.  In der folgenden Tabelle wird der Unterschied zwischen den beiden Syntaxformaten gezeigt.  
  
|Syntaxformat|Aktion|  
|------------------|------------|  
|Format mit Anführungszeichen|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> 1.  In dem Verzeichnis, in dem auch die Datei mit der `#include`\-Anweisung enthalten ist.<br />2.  In den Verzeichnissen der aktuell geöffneten Includedateien in umgekehrter Reihenfolge, in der sie geöffnet wurden.  Die Suche beginnt im Verzeichnis der übergeordneten Includedatei und wird nach oben durch die Verzeichnisse aller Includedateien der zweiten übergeordneten Ebene fortgesetzt.<br />3.  Entlang des Pfads, der durch die einzelnen \/I\-Compileroptionen angegeben wurde.<br />4.  Entlang der Pfade, die durch die INCLUDE\-Umgebungsvariable angegeben wurden.|  
|Format mit spitzer Klammer|Die Präprozessor sucht in dieser Reihenfolge nach Includedateien:<br /><br /> 1.  Entlang des Pfads, der durch die einzelnen \/I\-Compileroptionen angegeben wurde.<br />2.  Beim Kompilieren von der Befehlszeile entlang der Pfade, die durch die INCLUDE\-Umgebungsvariable angegeben werden.|  
  
 Der Präprozessor beendet die Suche, sobald eine Datei mit dem angegebenen Namen gefunden wird.  Wenn Sie eine vollständige, eindeutige Pfadangabe für die Includedatei zwischen doppelten Anführungszeichen \(" "\) angeben, sucht der Präprozessor nur diese Pfadangabe und ignoriert die Standardverzeichnisse.  
  
 Wenn der in doppelte Anführungszeichen eingeschlossene Dateiname eine unvollständige Pfadangabe ist, sucht der Präprozessor zuerst das Verzeichnis der "übergeordneten" Datei.  Eine übergeordnete Datei ist die Datei, in der die `#include`\-Direktive enthalten ist.  Wenn Sie beispielsweise eine Datei namens `file2` in eine Datei namens `file1` einschließen, ist `file1` die übergeordnete Datei.  
  
 Includedateien können "geschachtelt" werden, d. h. eine `#include`\-Direktive kann in einer Datei angezeigt werden, die durch eine andere `#include`\-Direktive benannt wurde.  `file2` kann beispielsweise `file3` enthalten.  In diesem Fall würde `file1` weiterhin das übergeordnete Element von `file2` sein und gleichzeitig die zweite übergeordnete Ebene von `file3`.  
  
 Wenn Includedateien geschachtelt sind und die Kompilierung von der Befehlszeile erfolgt, beginnt die Suche in den Verzeichnissen der übergeordneten Datei. Danach werden die Verzeichnisse aller Dateien der zweiten übergeordneten Ebene durchsucht.  Dies bedeutet, dass die Suche relativ zum Verzeichnis beginnt, das die Quelldatei enthält, die gerade verarbeitet wird.  Wenn die Datei nicht gefunden wird, wird die Suche in den durch die \/I\-Compileroption angegebenen Verzeichnissen fortgesetzt.  Zuletzt werden die durch die INCLUDE\-Umgebungsvariablen angegebenen Verzeichnisse durchsucht.  
  
 Aus der Entwicklungsumgebung wird die INCLUDE\-Umgebungsvariable ignoriert.  Weitere Informationen zum Festlegen der Verzeichnisse, die für die Includedateien durchsucht werden – dies gilt auch für die LIB\-Umgebungsvariable – finden Sie unter [VC\+\+ Directories, Projects, Options Dialog Box](assetId:///e027448b-c811-4c3d-8531-4325ad3f6e02).  
  
 In diesem Beispiel sehen Sie, wie mithilfe der spitzen Klammern Dateien in die Suche einbezogen werden:  
  
```  
#include <stdio.h>  
```  
  
 In diesem Beispiel wird der Inhalt der Datei namens STDIO.H dem Quellprogramm hinzugefügt.  Durch die spitzen Klammern werden vom Präprozessor zuerst die durch die \/I\-Compileroption angegebenen Verzeichnisse durchsucht und dann die durch die INCLUDE\-Umgebungsvariable für STDIO.H angegebenen Verzeichnisse.  
  
 Im nächsten Beispiel sehen Sie, wie mithilfe der Anführungszeichen Dateien in die Suche einbezogen werden:  
  
```  
#include "defs.h"  
```  
  
 In diesem Beispiel wird der Inhalt der durch DEFS.H angegebenen Datei dem Quellprogramm hinzugefügt.  Die doppelten Anführungszeichen bewirken, dass der Präprozessor zuerst das Verzeichnis mit der übergeordneten Quelldatei durchsucht.  
  
 Includedateien können auf bis zu 10 Ebenen geschachtelt werden.  Sobald die geschachtelte `#include`\-Datei verarbeitet ist, wird vom Präprozessor die einschließende Includedatei in die ursprüngliche Quelldatei eingefügt.  
  
 **Microsoft\-spezifisch**  
  
 Um die Quelldateien zu finden, die einbezogen werden können, durchsucht der Präprozessor zuerst die Verzeichnisse, die durch die \/I\- Compileroption angegeben werden.  Wenn die \/I\-Option nicht vorhanden ist oder Fehler auftreten, verwendet der Präprozessor die INCLUDE\-Umgebungsvariable, um alle Includedateien in spitzen Klammern zu suchen.  Die INCLUDE\-Umgebungsvariable und die \/I\-Compileroption können mehrere Pfade enthalten, die durch Semikolons \(;\) getrennt werden.  Wenn mehrere Verzeichnisse in der \/I\-Option oder der INCLUDE\-Umgebungsvariablen enthalten sind, werden diese vom Präprozessor in der Reihenfolge durchsucht, in der sie angezeigt werden.  
  
 Mit dem Befehl  
  
```  
CL /ID:\MSVC\INCLUDE MYPROG.C  
```  
  
 beispielsweise wird der Präprozessor veranlasst, das Verzeichnis D:\\MSVC\\INCLUDE\\ nach Includedateien wie STDIO.H. zu durchsuchen.  Die Befehle  
  
```  
SET INCLUDE=D:\MSVC\INCLUDE  
CL MYPROG.C  
```  
  
 haben dieselbe Wirkung.  Wenn es bei beiden Suchvorgängen zu Fehlern kommt, tritt ein schwerwiegender Compilerfehler auf.  
  
 Wenn der Dateiname für eine Includedatei mit einem Pfad, der einen Doppelpunkt enthält \(z. B. F:\\MSVC\\SPECIAL\\INCL\\TEST.H\) vollständig angegeben wurde, folgt der Präprozessor dem Pfad.  
  
 Für die Includedateien, die als `#include` "`path-spec`" angegeben sind, wird das Durchsuchen der Verzeichnisse in dem Verzeichnis der übergeordneten Datei gestartet und dann in den Verzeichnissen aller Dateien der zweiten übergeordneten Ebene fortgesetzt.  Daher beginnt die Suche relativ zum Verzeichnis, das die Quelldatei mit der `#include`\-Direktive enthält, die verarbeitet wird.  Wenn keine Datei der zweiten übergeordneten Ebene vorhanden ist und die Datei nicht gefunden wurde, wird die Suche so fortgesetzt, als ob der Dateiname in spitzen Klammern eingeschlossen wäre.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)