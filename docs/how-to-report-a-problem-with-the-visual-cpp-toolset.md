---
title: Melden eines Problems mit dem Visual C++-Toolset | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ec24a49c-411d-47ce-aa4b-8398b6d3e8f6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2ea129ac94cb1ddc7486ba69280dc0390896e088
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Melden eines Problems mit dem Visual C++-Toolset
Wenn Sie Probleme mit dem Visual C++-Compiler, -Linker oder anderen Tools haben, möchten wir davon erfahren.  
  
 Die beste Möglichkeit, uns über ein Problem zu informieren, ist das Senden eines Berichts mit einer Beschreibung des aufgetretenen Problems, mit Details dazu, wie Sie Ihr Programm entwickeln, und mit einem Codeausschnitt, den wir zum Reproduzieren des Problems auf unseren Computern nutzen können. Anhand dieser Informationen können wir rasch prüfen, ob das Problem existiert und nicht bloß lokal in Ihrer Umgebung vorliegt. Außerdem können wir bestimmen, ob es sich auf andere Versionen des Compilers auswirkt, und seine Ursache ermitteln.  
  
 In diesem Dokument geht es um Folgendes  
  
-   [Vorbereiten des Berichts](#prepare) und Merkmale eines guten Berichts.  
  
-   [Möglichkeiten zum Senden Ihres Berichts](#send) und deren Unterschiede.  
  
-   [Generieren einer Reproduktion](#generate) und verschiedene Arten von Reproduktionen.  
  
 Ihre Berichte sind wichtig für uns und andere Entwickler wie Sie. Vielen Dank für Ihren Beitrag zur Verbesserung von Visual C++!  
  
##  <a name="prepare"></a> Vorbereiten des Berichts  
 Das Erstellen eines Berichts hoher Qualität ist wichtig, da es sehr schwierig ist, das bei Ihnen aufgetretene Problem auf unseren Computern zu reproduzieren, wenn die Informationen nicht vollständig sind. Je besser Ihr Bericht, desto effektiver können wir das Problem reproduzieren und untersuchen.  
  
 Ihr Bericht sollte mindestens die folgenden Elemente enthalten:  
  
-   Die vollständigen Informationen zur Version des Toolsets, das Sie verwenden.  
  
-   Die vollständige „cl.exe“-Befehlszeile, die zum Erstellen Ihres Code verwendet wurde.  
  
-   Eine ausführliche Beschreibung des aufgetretenen Problems.  
  
-   Eine „Reproduktion“, d.h. Quellcode zum Veranschaulichen des Problems.  
  
 Lesen Sie weiter, um mehr über die spezifischen Informationen zu erfahren, die wir benötigen und wo Sie sie finden können.  
  
### <a name="the-toolset-version"></a>Die Version des Toolsets  
 Wir benötigen die vollständigen Versionsinformationen zum Toolset, das Sie verwenden, damit wir Ihre Reproduktion mit demselben Toolset auf unseren Computern testen können. Wenn wir das Problem reproduzieren können, verfügen wir über einen Ausgangspunkt, um zu untersuchen, welche anderen Versionen des Toolsets dasselbe Problem aufweisen.  
  
##### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>So melden Sie die vollständige Version des von Ihnen verwendeten Compilers  
  
1.  Drücken Sie auf der Tastatur die WINDOWS-TASTE, und beginnen Sie mit dem Eingeben von `Developer Command Prompt`.  
  
2.  Wählen Sie die Version der **Developer-Eingabeaufforderung**, die Ihrer Version von Visual Studio entspricht, sobald sie in der Liste der Suchergebnisse angezeigt wird.  
  
3.  Geben Sie in der Konsole **Developer-Eingabeaufforderung** den Befehl `cl /Bv /CLR` ein.  
  
 Die Ausgabe sollte etwa so aussehen:  
  
```  
C:\Compiler>cl /Bv /CLR  
Microsoft (R) C/C++ Optimizing Compiler Version 18.00.40209  
for Microsoft (R) .NET Framework version 4.00.30319.34014  
Copyright (C) Microsoft Corporation.  All rights reserved.  
  
Compiler Passes:  
 C:\WinCComp\binaries.x86chk\bin\i386\cl.exe:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1xx.dll:      Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c2.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\link.exe:      Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\mspdb120.dll:  Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\1033\clui.dll: Version 18.00.40209.0  
 Common Language Runtime:                            Version  4.00.30319.34014  
  
cl : Command line error D8003 : missing source filename   
```  
  
 Kopieren Sie die gesamte Ausgabe in den Bericht.  
  
### <a name="the-command-line"></a>Die Befehlszeile  
 Wir benötigen die vollständige Befehlszeile („cl.exe“ samt Argumenten), die verwendet wurde, um den Code zu erstellen, damit wir ihn auf exakt dieselbe Weise auf unseren Computer nachbilden können. Dies ist wichtig, da das aufgetretene Problem eventuell nur existiert, wenn der Build mit einem bestimmten Argument oder einer Kombination von Argumenten erstellt wird.  
  
 Diese Informationen finden Sie am besten unmittelbar nach Auftreten des Problems im Buildprotokoll. Dadurch wird sichergestellt, dass die Befehlszeile genau die gleichen Argumente enthält, die ggf. zum Problem beitragen.  
  
##### <a name="to-report-the-contents-of-the-command-line"></a>So melden Sie den Inhalt der Befehlszeile  
  
1.  Wechseln Sie zur Daten **CL.command.1.tlog**, und öffnen Sie sie. Standardmäßig befindet sich diese Datei unter \\...\Visual Studio Version\Projects\SolutionName\ProjectName\Config\ProjectName.tlog\CL.command.1.tlog.  
  
     In dieser Datei finden Sie die Namen von Quellcodedateien, gefolgt von den Befehlszeilenargumenten zu deren Kompilierung, jeweils in separaten Zeilen.  
  
2.  Suchen Sie die Zeile mit dem Namen der Quellcodedatei, in der das Problem auftritt. Die Zeile darunter enthält den entsprechenden cl.exe-Befehl und seine Argumente.  
  
 Kopieren Sie die gesamte Befehlszeile in den Bericht.  
  
### <a name="a-description-of-the-problem"></a>Eine Beschreibung des Problems  
 Wir benötigen eine ausführliche Beschreibung des aufgetretenen Problems, damit wir überprüfen können, ob es die gleiche Auswirkung auf unseren Computern hat. Außerdem ist es mitunter nützlich, von Ihnen zu erfahren, was Sie erreichen möchten und was Sie erwartet hatten.  
  
 Fügen Sie exakt die vom Toolset ausgegebenen Fehlermeldungen, eine Kurzbeschreibung ihrer Absicht, damit wir Ihren Reproduktionscode verstehen, und andere Details hinzu, mit deren Hilfe wir das bei Ihnen aufgetretene Problem untersuchen können, wie z.B. Problemumgehungen, die Sie ggf. gefunden haben. Vermeiden Sie die Wiederholung von Informationen, die an anderer Stelle in Ihrem Bericht vorhanden ist.  
  
### <a name="the-repro"></a>Die Reproduktion  
 Wir benötigen eine Reproduktion, d.h. ein eigenständiges Codebeispiel zum Demonstrieren des aufgetretenen Problems, damit wir den Fehler auf unseren Computern reproduzieren können. Die Art des aufgetretenen Problems bestimmt, welche Art von Reproduktion in den Bericht aufgenommen werden soll. Ohne geeignete Reproduktion gibt es nichts, was wir untersuchen könnten.  
  
 Kurze, eigenständige Reproduktionen können Sie direkt dem Berichtstext hinzufügen. Größere Quellcodereproduktionen sollten jedoch als Anlage an den Bericht angefügt werden. Reproduktionen, die nicht auf eine eine einzelne Quellcodedatei verkleinert werden können, sollten gepackt werden, indem ein Verzeichnis mit allen Dateien zu einer ZIP-Datei o.ä. komprimiert und an den Bericht angefügt wird. Alle weiteren szenariospezifischen Details sollten stets dem Berichtstext und nie dem Quellcode hinzugefügt werden.  
  
 Die beste Art der Reproduktion, die Sie uns bereitstellen können, ist eine *minimale Reproduktion*. Dies ist eine einzelne, eigenständige Quellcodedatei (ohne Verweise auf Benutzerheader), die gerade genug Code enthält, um das Problem zu demonstrieren. Wenn Sie eine Reproduktion in dieser Form bereitstellen können, fügen Sie die Quellcodedatei einfach an Ihren Bericht an, da dies alles ist, was wir brauchen.  
  
 Wenn Sie das Problem nicht auf eine minimale Reproduktion ohne Abhängigkeiten verkleinern können, finden Sie in den folgenden Abschnitten Informationen dazu, wie Sie die Art von Reproduktion bestimmen, die Sie Ihrem Bericht hinzufügen sollten.  
  
#### <a name="frontend-parser-crash"></a>Front-End-Absturz (in der Analysephase)  
 Front-End-Abstürze erfolgen in der Analysephase des Compilers. Der Compiler gibt in der Regel [Schwerwiegender Fehler C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) aus und verweist auf die Quellcodedatei und Zeilennummer, in der der Fehler aufgetreten ist. Häufig wird eine Datei des Typs „msc1.cpp“ erwähnt, die Sie jedoch ignorieren können.  
  
 Fügen Sie bei dieser Art des Absturzes eine [vorverarbeitete Reproduktion](#preprocessed_repro) hinzu.  
  
 Hier ist ein Beispiel der Ausgabe des Compilers bei dieser Art von Absturz:  
  
```  
SandBoxHost.cpp  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        fatal error C1001: An internal error has occurred in the compiler.  
(compiler file 'msc1.cpp', line 1369)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        note: This diagnostic occurred in the compiler generated function  
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'  
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted  
        to send an error report to Microsoft later.  
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information   
```  
  
####  <a name="backend_crash"></a> Back-End-Absturz (Codegenerierung)  
 Back-End-Abstürze erfolgen in der Codegenerierungsphase des Compilers. Der Compiler gibt in der Regel [Schwerwiegender Fehler C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) aus und verweist ggf. nicht auf die Quellcodedatei und Zeilennummer, in der das Problem aufgetreten ist. Häufig wird eine Datei des Typs „compiler\utc\src\p2\main.c“ erwähnt, was Sie jedoch ignorieren können.  
  
 Stellen Sie bei dieser Art des Absturzes bei Verwendung von Link-Zeitcodegenerierung (Link-Time Code Generation, LTCG) eine [Linkreproduktion](#link_repro) oder andernfalls eine [vorverarbeitete Reproduktion](#preprocessed_repro) bereit. LTGC wird aktiviert, indem „cl.exe“ das Befehlszeilenargument `/GL` angegeben wird.  
  
 Hier ist ein Beispiel der Ausgabe des Compilers bei dieser Art von Absturz, wenn LTCG **nicht** verwendet wird. Wenn Ihre Compilerausgabe wie folgt aussieht, sollten Sie eine [vorverarbeitete Reproduktion](#preprocessed_repro) bereitstellen.  
  
```  
repro.cpp  
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:  
        An internal error has occurred in the compiler.  
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
INTERNAL COMPILER ERROR in  
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information  
```  
  
 Wenn in der Zeile, die mit **Interner Compilerfehler** beginnt, „link.exe“ anstatt „cl.exe“ angegeben ist, war LTCG aktiviert, weshalb Sie eine [Linkreproduktion](#link_repro) bereitstellen sollten. Wenn anhand der Fehlermeldung des Compilers nicht klar ist, ob LTCG aktiviert war, müssen Sie möglicherweise die Befehlszeilenargumente untersuchen, die Sie in einem vorherigen Schritt aus dem Buildprotokoll für das Befehlszeilenargument `/GL` kopiert haben.  
  
#### <a name="linker-crash"></a>Linkerabstürze  
 Linkerabstürze treten in der Verknüpfungsphase nach Ausführung des Compilers auf. In der Regel gibt der Linker [Linkertoolfehler LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md) aus.  
  
> [!NOTE]
>  Wenn die Ausgabe C1001 oder LTCG enthält, finden Sie unter [Back-End-Absturz (Codegenerierung)](#backend_crash) weitere Informationen.  
  
 Fügen Sie bei dieser Art des Absturzes eine [Linkreproduktion](#link_repro) hinzu.  
  
 Hier ist ein Beispiel der Ausgabe des Compilers bei dieser Art von Absturz.  
  
```  
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2  
  
  Version 14.00.22816.0  
  
  ExceptionCode            = C0000005  
  ExceptionFlags           = 00000000  
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)  
        "z:\tools\bin\x64\link.exe"  
  NumberParameters         = 00000002  
  ExceptionInformation[ 0] = 0000000000000000  
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF  
  
CONTEXT:  
  
  Rax    = 0000000000000400  R8     = 0000000000000000  
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490  
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690  
  Rdx    = 000000655F97E270  R11    = 0000000000000400  
  Rsp    = 000000655F97E248  R12    = 0000000000000000  
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000  
  Rsi    = 000000655DF82580  R14    = 000000655F97F390  
  Rdi    = 0000000000000000  R15    = 0000000000000000  
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206  
  SegCs  = 0000000000000033  SegDs  = 000000000000002B  
  SegSs  = 000000000000002B  SegEs  = 000000000000002B  
  SegFs  = 0000000000000053  SegGs  = 000000000000002B  
  Dr0    = 0000000000000000  Dr3    = 0000000000000000  
  Dr1    = 0000000000000000  Dr6    = 0000000000000000  
  Dr2    = 0000000000000000  Dr7    = 0000000000000000  
```  
  
 Wenn inkrementelles Verknüpfen aktiviert ist und der Absturz nach dem anfänglichen Verknüpfen stattgefunden hat (d.h. erst nach der ersten vollständigen Verknüpfung, auf der nachfolgende inkrementelle Verknüpfungen basieren), fügen Sie eine Kopie der Objekt- und Bibliotheksdateien (OBJ und LIB) hinzu, die den Quelldateien entsprechen, die nach Abschluss der anfänglichen Verknüpfung geändert wurden.  
  
#### <a name="bad-code-generation"></a>Generierung von fehlerhaftem Code  
 Die Generierung von fehlerhaftem Code ist selten, erfolgt jedoch, wenn der Compiler versehentlich falschen Code erzeugt, der den Absturz Ihrer Anwendung zur Laufzeit bewirkt, anstatt dieses Problem zur Kompilierungszeit zu erkennen. Wenn Sie meinen, dass das aufgetretene Problem zur Generierung von fehlerhaftem Code führt, erstellen Sie Ihren Bericht analog zu [ Back-End-Absturz (Codegenerierung)](#backend_crash).  
  
 Stellen Sie bei dieser Art des Absturzes bei Verwendung von Link-Zeitcodegenerierung (Link-Time Code Generation, LTCG) eine [Linkreproduktion](#link_repro) oder andernfalls eine [vorverarbeitete Reproduktion](#preprocessed_repro) bereit. LTGC wird aktiviert, indem „cl.exe“ das Befehlszeilenargument `/GL` angegeben wird.  
  
##  <a name="send"></a> Möglichkeiten zum Senden Ihres Berichts  
 Es gibt mehrere Möglichkeiten, uns Ihren Bericht zu übermitteln. Sie können einen Fehler auf Microsoft Connect melden, uns eine E-Mail senden oder das in Visual Studio integrierte Tool „Problem melden“ verwenden. Die beste Wahl für Ihren Bericht hängt von der Art des aufgetretenen Problems und davon ab, wie Sie sich mit den Entwicklern austauschen möchten, die Ihren Bericht untersuchen. Ein weiterer Aspekt ist, ob Sie den Status nachverfolgen oder Ihren Bericht mit der Community teilen möchten.  
  
> [!NOTE]
>  Unabhängig davon, wie Sie den Bericht senden, respektiert Microsoft Ihre Privatsphäre. Informationen dazu, wie wir Daten behandeln, die Sie uns senden, finden Sie unter [Microsoft Visual Studio-Produktfamilie – Datenschutzbestimmungen](https://www.visualstudio.com/dn948229).  
  
### <a name="file-a-bug-on-microsoft-connect"></a>Melden eines Fehlers auf Microsoft Connect  
 Microsoft Connect ([connect.microsoft.com](http://connect.microsoft.com)) ist für unsere Benutzercommunity eine Möglichkeit, direkt mit den Teams in Verbindung zu treten, die Microsoft-Produkte entwickeln. Auf Connect können Sie neue Fehler melden und Anforderungen von Features stellen. Außerdem können Sie andere Fehler und Anforderungen der Community anzeigen und zum Ausdruck bringen, welche Ihnen am wichtigsten sind.  
  
 Das Melden des Problems auf Connect empfiehlt sich, wenn Sie Ihren Bericht mit der Visual Studio-Community teilen und den Status öffentlich verfolgen möchten. Indem Sie Ihren Bericht freigeben, haben andere die Möglichkeit, Problemumgehungen oder zusätzliche Informationen bereitzustellen, mit deren Hilfe wir das Problem untersuchen können. Sie können Connect aber auch nutzen, wenn Ihr Bericht privat bleiben soll (z.B. wenn Sie den Code in Ihrem Bericht nicht freigeben können). Legen Sie hierfür die Sichtbarkeit Ihres Berichts auf „Privat“ fest, ehe Sie das Formular übermitteln.  
  
-   [Microsoft Connect: Melden eines Problems mit Visual Studio 2015 Update 3](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6493)  
  
-   [Microsoft Connect: Melden eines Problems mit Visual Studio 2015 Update 2](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6406)  
  
-   [Microsoft Connect: Melden eines Problems mit Visual Studio 2015 Update 1](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6326)  
  
-   [Microsoft Connect: Melden eines Problems mit Visual Studio 2015](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6240)  
  
 Sie können ein Problem mit anderen Visual Studio- und .NET Framework-Produkten melden, indem Sie das Produkt in der Dropdownliste auf der Connect-Seite für [Feedback zu Visual Studio und .NET Framework](https://connect.microsoft.com/VisualStudio/feedback/LoadSubmitFeedbackForm) auswählen.  
  
### <a name="send-an-email"></a>Senden einer E-Mail  
 E-Mail ist eine weitere Möglichkeit, den Bericht direkt an das Visual C++-Team zu senden. Sie erreichen uns unter [compilercrash@microsoft.com](mailto:compilercrash@microsoft.com).  
  
 Bei Melden Ihres Problems per E-Mail steht die umfassende Community von Microsoft Connect nicht zur Verfügung, was aber für große Reproduktionen mitunter besser sein kann. Es kann außerdem die beste oder einzige Option sein, wenn Ihre Arbeitsumgebung nicht mit dem Internet verbunden ist oder Sie aus sonstigen Gründen nicht auf Microsoft Connect zurückgreifen können.  
  
 Wenn Sie den Bericht per E-Mail senden möchten, können Sie die folgende Vorlage als Text der E-Mail-Nachricht nutzen. Vergessen Sie nicht, Quellcode- oder andere Dateien anzufügen, wenn Sie diese Informationen nicht dem Text der E-Mail hinzugefügt haben.  
  
```  
To: compilercrash@microsoft.com  
Subject: Visual C++ Error Report  
-----  
  
Compiler version:  
  
CL.EXE command line:  
  
Problem description:  
  
Source code and repro steps:  
  
```  
  
### <a name="use-the-report-a-problem-tool"></a>Nutzen des Tools „Problem melden“  
 Das Tool „Problem melden“ in Visual Studio bietet Benutzern von Visual Studio die Möglichkeit, eine Vielzahl von Problemen über ein paar Mausklicks zu melden. Es bietet ein einfaches Formular, in dem Sie detaillierte Informationen zum aufgetretenen Problem angeben und Ihren Bericht anschließend übermitteln können, ohne die IDE verlassen zu müssen.  
  
 Das Melden Ihres Problems über das Tool „Problem melden“ ist allerdings nicht die Regel für die Arten von Toolsetproblemen, die in diesem Dokument behandelt werden. Dennoch ist es eine Option, die ggf. Ihren Vorlieben entspricht.  
  
> [!TIP]
>  Für andere Arten von Problemen, die ggf. in Visual Studio auftreten und ohne Beziehung zum Toolset sind (z.B. Probleme mit der Benutzeroberfläche, gestörte IDE-Funktionen oder allgemeine Abstürze), kann das Tool „Problem melden“ eine gute Wahl sein, und zwar aufgrund seiner Funktionen für Screenshots und zum Aufzeichnen von Aktionen auf der Benutzeroberfläche, die zum aufgetretenen Problem geführt haben. Microsoft Connect kann auch eine gute Wahl für die Berichterstattung dieser anderen Arten von Fehlern sein, bietet jedoch nicht die zusätzlichen Funktionen des Tools „Problem melden“. Diese anderen Arten von Fehlern dürfen Sie auf keinen Fall durch Senden einer E-Mail an compilercrash@microsoft.com melden.  
  
##  <a name="generate"></a> Generieren von Reproduktionen  
 Eine Reproduktion ist ein vollständiges und unabhängiges Codebeispiel, das das Problem veranschaulicht, das Sie melden. Eine Reproduktion ist **kein** Codeausschnitt, sondern muss ein vollständiges Beispiel sein, für das ein Build erstellt wird und die Ausführung erfolgt (bzw. erfolgen würde, wenn es die Probleme nicht gäbe, die Sie melden). Es muss alle erforderlichen #include-Direktiven, sogar für die Standardheader, enthalten.  
  
 Es folgen weitere Eigenschaften einer guten Reproduktion:  
  
-   **Minimal.** Reproduktionen sollte so klein wie möglich sein und dennoch das aufgetretene Problem exakt veranschaulichen. Reproduktionen müssen nicht unbedingt komplex oder realistisch, sondern sollten einfach und „auf den Punkt“ sein. Sie müssen auch keine Gegenbeispiele von Code hinzufügen, der funktioniert, können dies aber zur Veranschaulichung tun. Nur Beispielcode, der das Problem verursacht, ist erforderlich.  
  
-   **Unabhängig.** In Reproduktionen sollten unnötige Abhängigkeiten vermieden werden. Wenn Sie das Problem ohne Drittanbieterbibliotheken reproduzieren können, machen Sie dies. Wenn Sie das Problem ohne Bibliothekscode reproduzieren können (`std::out`, `printf()` sind zulässig), machen Sie dies. Für uns ist es enorm hilfreich, wenn Sie die Menge des Codes verringern, den wir als mögliche Ursache des Problems untersuchen müssen.  
  
-   **Neueste Compilerversion.** Reproduktionen müssen mit der neuesten Version des Toolsets erstellt werden. Probleme, die in älteren Versionen des Toolsets immer noch auftreten, wurden sehr häufig in neueren Versionen behoben.  
  
-   **Vergleich mit anderen Compilern**, falls relevant. Bei Reproduktionen, die portablen C++-Code enthalten, muss das Verhalten mit anderen Compilern, falls möglich, verglichen werden.  
  
     Dieser Schritt ist hilfreich, um zu bestimmen, ob der Code richtig ist, z.B. wenn MSVC nicht mit Clang und GCC übereinstimmt, oder falsch ist, wenn MSVC, Clang und GCC darin übereinstimmen, dass Ihr Code den Fehler erzeugt.  
  
 Es folgenden Anweisungen zum Generieren der verschiedenen Arten von Reproduktionen, mit deren Hilfe Sie verschiedene Arten von Problemen melden.  
  
###  <a name="preprocessed_repro"></a> Vorverarbeitete Reproduktionen  
 Eine vorverarbeitete Reproduktion ist eine einzelne Quelldatei, die ein Problem veranschaulicht und aus der Ausgabe des C-Präprozessors generiert wurde, indem die ursprüngliche Quelldatei verarbeitet wurde. Bei diesem Prozess wird für eingeschlossene Header „inline“ angegeben, um Abhängigkeiten von zusätzlichen Quell- und Headerdateien zu entfernen und zudem Makros, ifdefs und andere Präprozessorbefehle aufzulösen, die von Ihrer lokalen Umgebung abhängig sein könnten.  
  
> [!NOTE]
>  Beachten Sie, dass vorverarbeitete Reproduktionen für Probleme am unpraktischsten sind, die das Ergebnis von Fehlern in unserer Standardbibliotheksimplementierung sein können, da wir unsere neueste in Bearbeitung befindliche Implementierung häufig austauschen, um zu prüfen, ob wir das Problem bereits behoben haben. Führen Sie in diesem Fall keine Vorverarbeitung der Reproduktion aus. Wenn Sie das Problem nicht zu einer einzelne Quelldatei reduzieren können, packen Sie Ihren Code in eine ZIP-Datei o.ä., oder erwägen Sie eine IDE-Projektreproduktion (siehe [Andere Reproduktionen](#other_repros) weiter unten).  
  
##### <a name="to-preprocess-a-source-code-file"></a>So erfolgt die Vorverarbeitung einer Quellcodedatei  
  
1.  Drücken Sie auf der Tastatur die WINDOWS-TASTE, und beginnen Sie mit dem Eingeben von `Developer Command Prompt`.  
  
2.  Wählen Sie die Version der **Developer-Eingabeaufforderung**, die Ihrer Version von Visual Studio entspricht, sobald sie in der Liste der Suchergebnisse angezeigt wird.  
  
3.  Geben Sie im Fenster **Developer-Eingabeaufforderung** den Befehl `cl /P argumentsfilename.cpp` ein.  
  
 Nachdem Sie die Datei vorverarbeitet haben, (die jetzt DATEINAME.I heißt), empfiehlt es sich sicherzustellen, dass das Problem mithilfe der vorverarbeiteten Datei weiter reproduziert wird. Sie können das Befehlszeilenargument `/TP` verwenden, um „cl.exe“ anzuweisen, den Präprozessorschritt zu überspringen und eine Kompilierung wie üblich zu versuchen.  
  
##### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>So bestätigen Sie, dass der Fehler mit der vorverarbeiteten Datei weiter reproduziert wird  
  
1.  Drücken Sie auf der Tastatur die WINDOWS-TASTE, und beginnen Sie mit dem Eingeben von `Developer Command Prompt`.  
  
2.  Wählen Sie die Version der **Developer-Eingabeaufforderung**, die Ihrer Version von Visual Studio entspricht, sobald sie in der Liste der Suchergebnisse angezeigt wird.  
  
3.  Geben Sie im Fenster **Developer-Eingabeaufforderung** den Befehl `cl arguments /TP filename.i` ein.  
  
4.  Vergewissern Sie sich, dass das Problem reproduziert wird.  
  
 Fügen Sie schließlich diese Reproduktion an Ihren Bericht an.  
  
###  <a name="link_repro"></a> Linkreproduktionen  
 Eine Linkreproduktion ist ein einzelnes Verzeichnis mit Buildartefakten, die zusammen ein Problem veranschaulichen, das zur Verknüpfungszeit auftritt. Dies kann ein Back-End-Absturz bei Verwenden von LTCG (Link-Time Code Generation, Link-Zeitcodegenerierung) oder Linkerabsturz sein. Die enthaltenen Buildartefakte sind diejenigen, die als Linkereingabe benötigt werden, damit das Problem reproduziert werden kann. Linkreproduktionen können problemlos mithilfe der Funktionen erstellt werden, die der Linker bietet.  
  
##### <a name="to-generate-a-link-repro"></a>So generieren Sie eine Linkreproduktion:  
  
1.  Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie den Befehl `mkdir directory` zum Erstellen eines Verzeichnisses für die Linkreproduktion ein.  
  
2.  Legen Sie die Umgebungsvariable „link_repro“ auf das Verzeichnis fest, das Sie gerade erstellt haben, und geben Sie den Befehl `set link_repro=directory` ein.  
  
3.  Wenn der Buildvorgang in Visual Studio erfolgen soll, starten Sie ihn im Eingabeaufforderungsfenster durch Eingabe des Befehls `devenv`. Dadurch wird sichergestellt, dass der Wert der Umgebungsvariablen „link_repro“ für Visual Studio sichtbar ist.  
  
4.  Erstellen Sie die Anwendung, und vergewissern Sie sich, dass das erwartete Problem aufgetreten ist.  
  
5.  Schließen Sie Visual Studio jetzt, falls Sie es in Schritt 3 gestartet haben.  
  
6.  Löschen Sie die Umgebungsvariable „link_repro“. Geben Sie den Befehl `set link_repro=` ein.  
  
 Packen Sie abschließend die Reproduktion durch Komprimieren des gesamten Verzeichnisses in einer ZIP-Datei o.ä., und fügen Sie sie an Ihren Bericht an.  
  
###  <a name="other_repros"></a> Andere Reproduktionen  
 Wenn Sie das Problem nicht auf eine einzelne Quelldatei oder vorverarbeitete Reproduktion reduzieren können und das Problem keine Linkreproduktion verlangt, können wir ein IDE-Projekt untersuchen. Der Code im Projekt darf weiter nur minimal sein, wobei weiter alle in diesem Dokument beschriebenen Leitlinien gelten.  
  
 Erstellen Sie Ihre Reproduktion als minimales IDE-Projekt, und erstellen Sie dann ein Paket, indem Sie die gesamte Verzeichnisstruktur in einer ZIP-Datei o.ä. komprimieren und diese an Ihren Bericht anfügen.
