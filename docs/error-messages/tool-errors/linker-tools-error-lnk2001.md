---
title: "Linkertoolfehler LNK2001"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2001"
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht aufgelöstes externes Symbol "Symbol"  
  
 Im Code wird auf ein Element verwiesen \(z. B. eine Funktion, Variable oder Marke\), das der Linker in den Bibliotheken und Objektdateien nicht finden kann.  
  
 Auf diese Fehlermeldung folgt der schwerwiegende Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md).  
  
 **Mögliche Ursachen**  
  
-   Beim Aktualisieren einer verwalteten Bibliothek oder eines Webdienstprojekts von Visual C\+\+ 2003 wird die **\/Zl**\-Compileroption auf der Eigenschaftenseite für die **Befehlszeile** hinzugefügt.  Dadurch wird LNK2001 verursacht.  
  
     Um diesen Fehler zu beheben, fügen Sie der Eigenschaft Zusätzliche Abhängigkeiten des Linkers msvcrt.lib und msvcmrt.lib hinzu.  Oder entfernen Sie **\/Zl** auf der Eigenschaftenseite für die **Befehlszeile**.  Weitere Informationen finden Sie unter [\/Zl \(Kein Standardbibliotheksname\)](../../build/reference/zl-omit-default-library-name.md) und [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
-   Das im Code gesuchte Element ist nicht vorhanden \(das Symbol ist z. B. falsch geschrieben, oder die Groß\-\/Kleinschreibung ist fehlerhaft\).  
  
-   Im Code wird das falsche Element gesucht \(Sie verwenden gemischte Bibliotheksversionen – einige aus einer Produktversion und andere aus einer davon abweichenden Version\).  
  
 **Spezifische Ursachen**  
  
 **Probleme bei der Codierung**  
  
-   Wenn im Diagnosetext von LNK2001 angegeben ist, dass es sich bei `__check_commonlanguageruntime_version` um ein nicht aufgelöstes externes Symbol handelt, finden Sie unter [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) Informationen zum Beheben des Problems.  
  
-   Die Membervorlage wurde außerhalb der Klasse definiert.  Visual C\+\+ verfügt über eine Einschränkung, gemäß der Membervorlagen vollständig innerhalb der einschließenden Klasse definiert sein müssen.  Weitere Informationen über LNK2001 und Membervorlagen finden Sie im KB\-Artikel Q239436.  
  
-   Unterschiedliche Groß\-\/Kleinschreibung im Code oder der Moduldefinitionsdatei \(.def\) können LNK2001 verursachen.  Beispiel: Sie haben eine Variable in einer C\+\+\-Quelldatei mit `var1` benannt und versucht, von einer anderen Quelldatei aus auf diese Variable als `VAR1` zuzugreifen.  
  
-   Ein Projekt, das [Inlinefunktionen](../../error-messages/tool-errors/function-inlining-problems.md) verwendet und die Funktionen noch in einer CPP\-Datei anstatt in der Headerdatei definiert, kann LNK2001 auslösen.  
  
-   Der Aufruf einer C\-Funktion aus einem C\+\+\-Programm ohne Verwendung von `extern` "C" \(wodurch der Compiler angewiesen wird, die C\-Namenskonvention zu verwenden\) kann LNK2001 verursachen.  Durch die Compileroptionen [\/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) und [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) werden Dateien vom Compiler unabhängig von der Dateinamenerweiterung als C\- bzw. C\+\+\-Dateien kompiliert.  Diese Optionen können zu unerwarteten Funktionsnamen führen.  
  
-   Beim Versuch, auf Funktionen oder Daten zu verweisen, die über keine externe Bindung verfügen, kann LNK2001 ausgelöst werden.  In C\+\+ sind Inlinefunktionen und `const`\-Daten intern verknüpft, sofern sie nicht explizit als `extern` deklariert werden.  
  
-   Durch einen [fehlenden Funktionsrumpf oder eine fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md) kann ebenfalls LNK2001 ausgelöst werden.  Wenn einfach nur ein Funktionsprototyp oder eine `extern`\-Deklaration vorhanden ist, setzt der Compiler die Verarbeitung zwar ohne Fehler fort, der Linker ist jedoch nicht in der Lage, einen Aufruf einer Adresse oder einen Verweis auf eine Variable aufzulösen, da kein Platz für den Funktionscode oder die Variable reserviert ist.  
  
-   Durch den Aufruf von Funktionen mit Parametertypen, die nicht mit denen in der Funktionsdeklaration übereinstimmen, kann LNK2001 verursacht werden.  Bei der [Namensergänzung](../../error-messages/tool-errors/name-decoration.md) werden die Parameter einer Funktion in den endgültigen ergänzten Funktionsnamen übernommen.  
  
-   Prototypen, die nicht korrekt eingelesen wurden und zur Folge haben, dass der Compiler einen nicht verfügbaren Funktionsrumpf erwartet, können LNK2001 verursachen.  Wenn Sie eine Implementierung einer Funktion `F` mit und ohne Klassen verwenden, müssen Sie die C\+\+\-Regeln für die Bereichsauflösung beachten.  
  
-   Wenn bei Verwendung von C\+\+ ein Funktionsprototyp in eine Klassendefinition eingeschlossen wird, ohne dass auch die [Implementierung eingeschlossen](../../error-messages/tool-errors/missing-function-body-or-variable.md) wird, die zu der Funktion dieser Klasse gehört, kann LNK2001 verursacht werden.  
  
-   Der Versuch, eine rein virtuelle Funktion vom Konstruktor oder Destruktor einer abstrakten Basisklasse aufzurufen, kann LNK2001 verursachen.  Eine rein virtuelle Funktion verfügt über keine Basisklassenimplementierung.  
  
-   Der Versuch, eine innerhalb einer Funktion deklarierte Variable \([eine lokale Variable](../../error-messages/tool-errors/automatic-function-scope-variables.md)\) außerhalb des Gültigkeitsbereichs dieser Funktion zu verwenden, kann LNK2001 zur Folge haben.  
  
-   Beim Erstellen einer Releaseversion eines ATL\-Projekts weist die Fehlermeldung darauf hin, dass CRT\-Startcode erforderlich ist.  Sie können diese Situation durch einen der folgenden Schritte korrigieren:  
  
    -   Entfernen Sie `_ATL_MIN_CRT` aus der Liste der Präprozessordefinitionen, damit CRT\-Startcode eingebunden werden kann.  Weitere Informationen finden Sie unter [Eigenschaftenseite "Allgemein" \(Projekt\)](../../ide/general-property-page-project.md).  
  
    -   Entfernen Sie, falls möglich, Aufrufe von CRT\-Funktionen, die CRT\-Startcode benötigen.  Verwenden Sie stattdessen ihre Win32\-Äquivalente.  Verwenden Sie beispielsweise `lstrcmp` anstelle von `strcmp`.  Zu den Funktionen, die CRT\-Startcode erfordern, gehören bekannterweise einige Zeichenfolgen\- und Gleitkommafunktionen.  
  
 **Probleme beim Kompilieren und Verknüpfen**  
  
-   Im Projekt fehlt ein Verweis auf eine Bibliotheksdatei \(.lib\) oder Objektdatei \(.obj\).  Weitere Informationen finden Sie unter [LIB\-Dateien als Eingabe für den Linker](../../build/reference/dot-lib-files-as-linker-input.md).  
  
-   Wenn Sie [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) oder [\/Zl](../../build/reference/zl-omit-default-library-name.md) verwenden, werden Bibliotheken mit erforderlichem Code nicht im Projekt eingebunden, solange Sie sie nicht explizit einfügen. \(Beim Kompilieren mit **\/clr** oder **\/clr:pure** wird ein Verweis auf .cctor angezeigt. Weitere Informationen hierzu finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md)\).  
  
-   Wenn Sie bei Verwendung von Unicode und MFC keinen Einstiegspunkt für `wWinMainCRTStartup` erstellen, erhalten Sie einen nicht aufgelösten externen Verweis auf `_WinMain@16`. Verwenden Sie [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  Siehe [Zusammenfassung der Unicode\-Programmierung](../../text/unicode-programming-summary.md).  
  
     Weitere Informationen finden Sie in den folgenden Knowledge Base\-Artikeln in der MSDN Library.  Klicken Sie in der MSDN Library auf die Registerkarte **Suchen**, fügen Sie die Artikelnummer oder den Titel in das Textfeld ein, und klicken Sie anschließend auf **Themen auflisten**.  Wenn Sie nach der Artikelnummer suchen, vergewissern Sie sich, dass die Option **Nur in Titeln suchen** deaktiviert ist.  
  
    -   Q125750   "PRB: Error LNK2001: '\_WinMain@16': Unresolved External Symbol" \(nur auf Englisch verfügbar\)  
  
    -   Q131204   "PRB: Wrong Project Selection Causes LNK2001 on \_WinMain@16" \(nur auf Englisch verfügbar\)  
  
    -   Q100639   "Unicode Support in the Microsoft Foundation Class Library" \(nur auf Englisch verfügbar\)  
  
    -   Q291952    "PRB: Link Error LNK2001: Unresolved External Symbol \_main" \(nur auf Englisch verfügbar\)  
  
-   Wenn Sie Code, der unter Verwendung von \/MT kompiliert wurde, mit der Bibliothek LIBC.lib verknüpfen, wird für `_beginthread`, `_beginthreadex`, `_endthread` und `_endthreadex` der Fehler LNK2001 ausgegeben.  
  
-   Beim Verknüpfen von Code, der die Multithreadbibliotheken erfordert \(beliebiger MFC\-Code oder mit [\/MT](../../build/reference/md-mt-ld-use-run-time-library.md) kompilierter Code\) wird LNK2001 für [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [\_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) und `_endthreadex` ausgegeben.  Weitere Informationen finden Sie in den folgenden Knowledge Base\-Artikeln:  
  
    -   Q126646 "PRB: Error Msg: LNK2001 on \_\_beginthreadex and \_\_endthreadex" \(nur auf Englisch verfügbar\)  
  
    -   Q128641 "INFO: \/Mx Compiler Options and the LIBC, LIBCMT, MSVCRT Libs" \(nur auf Englisch verfügbar\)  
  
    -   Q166504 "PRB: MFC and CRT Must Match in debug\/release and static\/dynamic" \(nur auf Englisch verfügbar\)  
  
-   Beim Kompilieren mit **\/MD** wird der Verweis auf "func" im Quellcode in einen Verweis mit dem Namen "`__imp__func`" im Objekt umgewandelt, da die gesamte Laufzeit nun in einer DLL enthalten ist.  Wenn Sie versuchen, eine Verknüpfung mit den statischen Bibliotheken LIBC.lib oder LIBCMT.lib zu erstellen, tritt bei `__imp__func` der Fehler LNK2001 auf.  Wenn Sie beim Kompilieren ohne \/MD versuchen, eine Verknüpfung mit MSVCxx.lib herzustellen, wird LNK2001 nicht immer ausgelöst, es können jedoch andere Probleme auftreten.  
  
-   Wenn Sie eine Debugversion einer Anwendung erstellen, kann durch das Verknüpfen mit den Releasemodusbibliotheken LNK2001 verursacht werden.  Ebenso führt das Verwenden einer **\/Mxd**\-Option \(**\/MTd** oder **\/MDd**\) und\/oder Definieren von `_DEBUG` und anschließendes Verknüpfen mit den Releasebibliotheken unter Umständen zu nicht aufgelösten externen Verweisen \(neben anderen Problemen\).  Zu ähnlichen Problemen führt das Verknüpfen eines Releasemodusbuilds mit den Debugbibliotheken.  
  
-   Das Kombinieren unterschiedlicher Versionen der Microsoft\-Bibliotheken und Compilerprodukte kann problematisch sein.  Die Bibliotheken einer neuen Compilerversion können neue Symbole enthalten, die in den Bibliotheken älterer Versionen nicht gefunden werden können.  Sie können die Reihenfolge der Verzeichnisse im Suchpfad ändern oder die Verzeichnisse so festlegen, dass sie auf die aktuelle Version zeigen.  
  
     Im Dialogfeld VC\+\+\-Verzeichnisse \(Extras &#124; Optionen &#124; Projekte\) unter der Auswahl Bibliothekdateien können Sie die Suchreihenfolge ändern.  Im Ordner Linker der projektspezifischen Eigenschaftenseiten sind u. U. weitere Pfade enthalten, die nicht mehr aktuell sind.  
  
     Dieses Problem kann bei der Installation eines neuen SDKs \(möglicherweise an einem neuen Speicherort\) auftreten, wenn die Suchreihenfolge nicht an den neuen Speicherort angepasst wird.  Normalerweise sollte der Pfad zu den Include\- und Bibliotheksverzeichnissen des neuen SDKs vor dem Visual C\+\+\-Standardverzeichnis angegeben werden.  Außerdem kann ein Projekt mit eingebetteten Pfaden weiterhin auf alte Pfade verweisen, die zwar immer noch gültig sind, in Bezug auf neue Funktionen, die von der neuen Version an einem anderen Speicherort bereitgestellt werden, jedoch veraltet sein können.  
  
-   Im Hinblick auf die [C\+\+\-Namensergänzung](../../error-messages/tool-errors/name-decoration.md) gibt es unter Compilerherstellern und selbst zwischen verschiedenen Compilerversionen derzeit keinen Standard.  Daher wird beim Verknüpfen von Objektdateien, die mit anderen Compilern erstellt wurden, u. U. nicht dasselbe Namensschema erstellt und somit Fehler LNK2001 ausgegeben.  
  
-   [Das Kombinieren von Inline\- und Nicht\-Inlinekompilierungsoptionen](../../error-messages/tool-errors/function-inlining-problems.md) bei unterschiedlichen Modulen kann LNK2001 verursachen.  Dieser Fehler tritt auf, wenn eine C\+\+\-Bibliothek mit aktivierten Inlinefunktionen \(**\/Ob1** oder **\/Ob2**\) erstellt wird, Inlinefunktionen in der zugehörigen Headerdatei mit den Funktionsbeschreibungen jedoch deaktiviert sind \(kein `inline`\-Schlüsselwort vorhanden\).  Um dieses Problem zu vermeiden, definieren Sie die Inlinefunktionen mit `inline` in der Headerdatei, die Sie in andere Dateien einbinden möchten.  
  
-   Bei Verwendung der `#pragma inline_depth`\-Compilerdirektive sollten Sie sicherstellen, dass [mindestens der Wert 2 festgelegt wurde](../../error-messages/tool-errors/function-inlining-problems.md), und dass Sie die [\/Ob1](../../build/reference/ob-inline-function-expansion.md)\-Compileroption oder die [\/Ob2](../../build/reference/ob-inline-function-expansion.md)\-Compileroption verwenden.  
  
-   Wenn Sie die LINK\-Option \/NOENTRY beim Erstellen einer reinen Ressourcen\-DLL nicht angeben, wird LNK2001 ausgegeben.  
  
-   Die Verwendung ungültiger Einstellungen für \/SUBSYSTEM oder \/ENTRY kann LNK2001 verursachen.  Wenn Sie z. B. eine zeichenbasierte Anwendung \(Konsolenanwendung\) entwickeln und \/SUBSYSTEM:WINDOWS angeben, kann ein externer Verweis auf `WinMain` nicht aufgelöst werden.  Weitere Informationen über diese Optionen und Einstiegspunkte finden Sie unter den Linkeroptionen [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) und [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 **Probleme beim Exportieren**  
  
-   Beim Portieren einer Anwendung von 16 Bits auf 32 Bits oder 64 Bits kann LNK2001 auftreten.  Die Syntax für die aktuelle Moduldefinitionsdatei \(.def\) erfordert, dass die Funktionen `__cdecl`, `__stdcall` und `__fastcall` im EXPORTS\-Abschnitt ohne Unterstriche \(nicht ergänzt\) aufgelistet werden.  Dies stellt eine Abweichung zur 16\-Bit\-Syntax dar, in der die Funktionen mit Unterstrichen \(ergänzt\) aufgeführt sein müssen.  Weitere Informationen finden Sie in der Beschreibung zum [EXPORTS](../../build/reference/exports.md)\-Abschnitt für Moduldefinitionsdateien.  
  
-   Jeder in der DEF\-Datei aufgeführte, jedoch nicht gefundene Export verursacht LNK2001.  Dies trifft z. B. zu, wenn der Export nicht vorhanden ist, ein Schreibfehler vorliegt oder ergänzte C\+\+\-Namen verwendet werden \(DEF\-Dateien akzeptieren keine ergänzten Namen\).  
  
 **Interpretieren der Ausgabe**  
  
 Wenn ein Symbol nicht aufgelöst wird, erhalten Sie anhand der folgenden Richtlinien Informationen über die Funktion:  
  
 Auf x86\-Plattformen lautet die Aufrufkonvention für ergänzte Namen, die in C kompiliert wurden, bzw. für Namen in C\+\+, die mit extern "C" kompiliert wurden, wie folgt:  
  
 `__cdecl`  
 Die Funktion hat ein Präfix in Form eines Unterstrichs \(\_\).  
  
 `__stdcall`  
 Die Funktion hat ein Präfix in Form eines Unterstrichs \(\_\) und ein @\-Suffix, gefolgt von der in einem DWORD ausgerichteten Größe der Parameter auf dem Stapel.  
  
 `__fastcall`  
 Die Funktion hat ein @\-Präfix und ein @\-Suffix, gefolgt von der in einem DWORD ausgerichteten Größe der Parameter auf dem Stapel.  
  
 Um die nicht ergänzte Form eines ergänzten Namens zu erhalten, verwenden Sie undname.exe.  
  
 Weitere Informationen zu einigen der oben genannten Ursachen finden Sie unter [Namensergänzung](../../error-messages/tool-errors/name-decoration.md).