---
title: Linkertoolfehler Lnk2001 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9dee257bec0f09bd729bf10c4a1468ecb20dfa61
ms.openlocfilehash: 3629075e5659cb89ab751b011f3ce2cbf89397cc
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2001"></a>Linkertoolfehler LNK2001
nicht aufgelöstes externes Symbol "Symbol"  
  
 Code verweist auf ein Element (z. B. eine Funktion, eine Variable oder eine Bezeichnung), das der Linker in den Bibliotheken und Objektdateien finden kann.  
  
 Diese Fehlermeldung wird gefolgt von Schwerwiegender Fehler [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md).  
  
 **Mögliche Ursachen**  
  
-   Beim Aktualisieren einer verwalteten Bibliothek oder eines Webdienstprojekts von Visual C++ 2003 wird die **Zl** Compileroption wurde hinzugefügt, um die **Befehlszeile** Eigenschaftenseite. Dadurch wird LNK2001 verursacht.  
  
     Hinzuzufügen Sie zum Beheben dieses Fehlers entweder msvcrt.lib und msvcmrt.lib, der Linker Additional Dependencies-Eigenschaft. Entfernen **Zl** aus der **Befehlszeile** Eigenschaftenseite. Weitere Informationen finden Sie unter [/Zl (Omit Default Library Name)](../../build/reference/zl-omit-default-library-name.md) und [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
-   Im Code gesuchte ist nicht vorhanden (das Symbol ist falsch geschrieben oder die falsche Schreibweise, zum Beispiel verwendet).  
  
-   Der Code fragt das falsche Element gesucht (gemischte Versionen der Bibliotheken, einige aus einer Produktversion und andere aus einer anderen Version verwenden).  
  
 **Spezifische Ursachen**  
  
 **Probleme bei der Codierung**  
  
-   Wenn im Diagnosetext von LNK2001, dass meldet `__check_commonlanguageruntime_version` ist ein nicht aufgelöstes externes Symbol finden Sie unter [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) Informationen zum lösen.  
  
-   Die Definition der Membervorlage ist außerhalb der Klasse. Visual C++ verfügt über eine Einschränkung, die in der Membervorlagen vollständig innerhalb der einschließenden Klasse definiert werden müssen. Finden Sie im Knowledge Base-Artikel Q239436 für Weitere Informationen über LNK2001 und Membervorlagen aus.  
  
-   Unterschiedliche Groß-/Kleinschreibung im Code oder der Moduldefinitionsdatei (.def) können LNK2001. Beispielsweise, wenn Sie eine Variable namens `var1` in einer C++-Quelldatei und als zugreifen wollten, `VAR1` in einer anderen.  
  
-   Ein Projekt, verwendet [inlineersetzung](../../error-messages/tool-errors/function-inlining-problems.md) die Funktionen noch in einer CPP-Datei definiert wird, anstatt in der Kopfzeile LNK2001 auslösen können.  
  
-   Aufrufen einer C-Funktion aus einem C++-Programm ohne `extern` "C" (wodurch den Compiler die C-Namenskonvention zu verwenden) kann LNK2001. Compileroptionen [/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) und [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) bewirken, dass der Compiler Dateien als C++ oder C#, unabhängig von der Erweiterung bzw. kompilieren. Diese Optionen können dazu führen, dass Funktionsnamen aus als erwartet.  
  
-   Versucht, auf Funktionen oder Daten, die externen Bindung verfügen, kann LNK2001 verursacht werden. In C++ sind Inlinefunktionen und `const` Daten eine interne Bindung haben, sofern nicht ausdrücklich angegeben als `extern`.  
  
-   Ein [fehlender Funktionsrumpf oder fehlende Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md) kann ebenfalls LNK2001 verursacht. Nur ein Funktionsprototyp oder `extern` Deklaration der Compiler ohne Fehler fort, aber der Linker kann einen Aufruf einer Adresse oder Verweis auf eine Variable auflösen, da kein Funktionscode Variable reservierte Speicherplatz oder.  
  
-   Aufrufen einer Funktion mit Parametertypen, die nicht mit denen in der Funktionsdeklaration übereinstimmen, kann LNK2001 verursacht werden. [Nennen Sie die Dekoration](../../error-messages/tool-errors/name-decoration.md) fügen die Parameter einer Funktion in den endgültigen ergänzten Funktionsnamen ein.  
  
-   Falsch können in Prototypen, die bewirken, dass der Compiler einen Funktionsrumpf erwartet, die nicht LNK2001 verursacht werden. Wenn Sie eine Klasse und die nicht-Klasse eine Implementierung einer Funktion verfügen `F`, C++ Bereichsauflösungsoperator Regeln beachten.  
  
-   Wenn Sie C++ verwenden, z. B. einen Funktionsprototyp in eine Klassendefinition und Fehler bei der [enthalten die Implementierung](../../error-messages/tool-errors/missing-function-body-or-variable.md) der Funktion für diese Klasse kann ebenfalls LNK2001 verursachen.  
  
-   Versuch, eine reine virtuelle Funktion vom Konstruktor oder Destruktor einer abstrakten Basisklasse aufzurufen, kann LNK2001 verursacht werden. Eine reine virtuelle Funktion verfügt über keine Implementierung der Basisklasse.  
  
-   Innerhalb einer Funktion deklariert eine Variable verwenden möchten ([eine lokale Variable](../../error-messages/tool-errors/automatic-function-scope-variables.md)) außerhalb des Bereichs dieser Funktion kann LNK2001.  
  
-   Beim Erstellen einer Releaseversion eines ATL-Projekts gibt an, dass CRT-Startcode erforderlich ist. Um zu beheben, führen Sie eine der folgenden  
  
    -   Entfernen Sie `_ATL_MIN_CRT` aus der Liste der Präprozessor definiert werden, damit CRT-Startcode enthalten sein kann. Finden Sie unter [Configuration Settings Eigenschaftenseite Allgemein](../../ide/general-property-page-project.md) Weitere Informationen.  
  
    -   Entfernen Sie wenn möglich, Aufrufe von CRT-Funktionen, die CRT-Startcode erfordern. Verwenden Sie stattdessen ihre Win32-äquivalente. Verwenden Sie z. B. `lstrcmp` anstelle von `strcmp`. Bekannte Funktionen, die CRT-Startcode erfordern sind Teil der Zeichenfolge und Gleitkommafunktionen.  
  
 **Kompilieren und verknüpfen Probleme**  
  
-   Im Projekt fehlt einen Verweis auf eine Bibliothek (. LIB) oder ein Objekt (. OBJ)-Datei. Finden Sie unter [LIB-Dateien als Linkereingabe](../../build/reference/dot-lib-files-as-linker-input.md) Weitere Informationen.  
  
-   Bei Verwendung von [NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) oder [Zl](../../build/reference/zl-omit-default-library-name.md), Bibliotheken mit erforderlichem Code werden nicht in das Projekt verknüpft werden, es sei denn, Sie explizit angegeben haben. (Beim Kompilieren mit **/CLR** oder **/CLR: pure**, sehen Sie einen Verweis auf .cctor; Siehe [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md) Weitere Informationen.)  
  
-   Wenn Sie Unicode- und MFC verwenden, erhalten Sie einen nicht aufgelösten externen auf `_WinMain@16` Wenn Sie keinen Entrypoint zum Erstellen `wWinMainCRTStartup`; verwenden Sie die [Einstiegspunktfunktion](../../build/reference/entry-entry-point-symbol.md). Finden Sie unter [Zusammenfassung der Unicode-Programmierung](../../text/unicode-programming-summary.md).  
  
     Finden Sie unter den folgenden Knowledge Base-Artikeln, befindet sich in der MSDN-Bibliothek für Weitere Informationen. Klicken Sie in der MSDN Library auf der **Suche** , fügen Sie die Artikelnummer oder den Titel in das Textfeld, und klicken Sie dann auf **Themenliste**. Wenn Sie nach der Artikelnummer suchen, vergewissern Sie sich die **nur Titel suchen** Option ist deaktiviert.  
  
    -   Q125750 "PRB: Error LNK2001: '_WinMain@16': ein nicht aufgelöstes externes Symbol"  
  
    -   Q131204 "PRB: falsche Projektauswahl für Lnk2001 _WinMain@16"  
  
    -   Q100639 "Unicode-Unterstützung in Microsoft Foundation Class Library"  
  
    -   Q291952 "PRB: Link Error LNK2001: nicht aufgelöstes externes Symbol _main"  
  
-   Verknüpfen von Code mit/MT kompiliert wird, mit der Bibliothek LIBC.lib LNK2001 auf `_beginthread`, `_beginthreadex`, `_endthread`, und `_endthreadex`.  
  
-   Beim Verknüpfen von Code, der die Multithreadbibliotheken (MFC-Code oder mit kompiliertem Code [/MT](../../build/reference/md-mt-ld-use-run-time-library.md)) für LNK2001 [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md), `_beginthreadex`, [_endthread](../../c-runtime-library/reference/endthread-endthreadex.md), und `_endthreadex`. Finden Sie im folgenden Artikel der Knowledge Base weitere Informationen:  
  
    -   Q126646 "PRB: Error Msg: LNK2001 on __beginthreadex und \__endthreadex"  
  
    -   Q128641 "INFO: /Mx Compileroptionen und LIBC, LIBCMT, MSVCRT Libs"  
  
    -   Q166504 "PRB: MFC- und CRT-Debug-Version und statischen und dynamischen übereinstimmen"  
  
-   Beim Kompilieren mit **/MD**, ein Verweis auf "Func" im Quellcode wird der Verweis "`__imp__func`" in dem Objekt, da alle Laufzeit nun in einer DLL enthalten ist. Wenn Sie versuchen, eine Verknüpfung mit den statischen Bibliotheken LIBC.lib oder LIBCMT.lib, wird LNK2001 auf `__imp__func`. Wenn Sie versuchen, eine Verknüpfung mit MSVCxx.lib herzustellen, beim Kompilieren ohne/MD wird LNK2001 nicht immer, aber haben Sie wahrscheinlich andere Probleme.  
  
-   Verknüpfen mit dem Modus beim Erstellen einer Debugversion einer Anwendung kann LNK2001 verursacht werden. Auf ähnliche Weise mithilfe einer **MXD** Option (**/MTd**, oder **/MDd**) und/oder definieren `_DEBUG` und anschließendes Verknüpfen mit der Version gibt Ihnen potenzielle nicht aufgelöste externe (neben anderen Problemen). Verknüpfen einen Releasebuild der Modus mit den Debugbibliotheken bewirkt auch ähnliche Probleme auftreten.  
  
-   Verwenden verschiedener Versionen von Microsoft-Bibliotheken und Compiler-Produkte kann problematisch sein. Bibliotheken einer neuen Compilerversion können neue Symbole enthalten, die in den Bibliotheken mit früheren Versionen nicht gefunden werden kann. Möglicherweise möchten die Reihenfolge der Verzeichnisse im Suchpfad bzw. ändern Sie diese auf die aktuelle Version zu ändern.  
  
     Die Tools | Optionen | Projekte | Im Dialogfeld VC++-Verzeichnisse unter der Bibliothek Dateiauswahl können Sie die Suchreihenfolge ändern. Eigenschaftenseiten des Projekts im Ordner Linker kann auch Pfade enthalten, die veraltet sein könnten.  
  
     Dieses Problem kann auftreten, wenn ein neues SDK (z. B. an einen anderen Speicherort) installiert ist, und die Suchreihenfolge nicht aktualisiert wird, um auf den neuen Speicherort verweist. In der Regel platzieren Sie den Pfad zum neuen SDKs enthalten und lib-Verzeichnisse vor der Visual C++-Standardverzeichnis. Außerdem kann ein Projekt mit eingebetteten Pfaden weiterhin auf alte Pfade verweisen, die gültig, aber für neue Funktionen hinzugefügt, indem die neue Version, die an einem anderen Speicherort installiert ist veraltet.  
  
-   Es gibt derzeit keinen Standard für [C++-Benennung](../../error-messages/tool-errors/name-decoration.md) zwischen compileranbietern oder sogar zwischen unterschiedlichen Versionen eines Compilers. Daher Verknüpfen von Objektdateien, die mit anderen Compilern kompiliert möglicherweise nicht die gleichen Benennungsschema und somit Fehler LNK2001 verursacht.  
  
-   [Vermischen von Inline- und nicht Kompilierungsoptionen](../../error-messages/tool-errors/function-inlining-problems.md) bei unterschiedlichen Modulen kann LNK2001. Wenn eine C++-Bibliothek mit Inlinefunktionen eingeschaltet erstellt wird (**"/ Ob1"** oder **Ob2**) jedoch die entsprechende Headerdatei beschreiben die Funktionen inlining deaktiviert (kein `inline` Schlüsselwort), diese Fehlermeldung wird angezeigt. Um dieses Problem zu vermeiden, haben die Inlinefunktionen mit `inline` in der Headerdatei, die Sie in andere Dateien einbinden möchten.  
  
-   Bei Verwendung der `#pragma inline_depth` Compiler, stellen Sie sicher, Sie haben eine [Wert 2 oder höher festgelegt](../../error-messages/tool-errors/function-inlining-problems.md), und stellen Sie sicher, dass Sie die ["/ Ob1"](../../build/reference/ob-inline-function-expansion.md) oder [Ob2](../../build/reference/ob-inline-function-expansion.md) (Compileroption).  
  
-   Ohne die LINK-Option wird/NOENTRY beim Erstellen einer reinen Ressourcen-DLL LNK2001 verursacht.  
  
-   Mit falschen/Subsystem oder die Einstiegspunktfunktion kann LNK2001 verursacht werden. Z. B. Wenn Sie eine Anwendung anhand von Zeichen (Konsolenanwendung schreiben), und geben Sie die/Subsystem: Windows, erhalten Sie einen nicht aufgelösten externen für `WinMain`. Weitere Informationen über diese Optionen und Einstiegspunkte finden Sie unter der [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) und [Einstiegspunktfunktion](../../build/reference/entry-entry-point-symbol.md) Linkeroptionen.  
  
 **Probleme beim Exportieren**  
  
-   Beim Portieren von einer Anwendung von 16, 32 oder 64 Bits kann LNK2001 auftreten. Die Syntax für die aktuelle Moduldefinitionsdatei (.def) erfordert, dass `__cdecl`, `__stdcall`, und `__fastcall` Funktionen im EXPORTS-Abschnitt ohne Unterstriche (nicht ergänzt) aufgelistet werden. Dies unterscheidet sich von der 16-Bit-Syntax, in dem sie mit Unterstrichen (ergänzt) aufgeführt sein muss. Weitere Informationen finden Sie unter der Beschreibung der [EXPORTE](../../build/reference/exports.md) Abschnitt der DEF-Dateien.  
  
-   Exportieren von in der DEF-Datei aufgelistet und nicht gefunden wird LNK2001 verursacht. Möglicherweise ist nicht vorhanden, ist falsch geschrieben oder anhand von ergänzte C++-Namen (DEF-Dateien nehmen nicht ergänzte Namen)  
  
 **Interpretieren der Ausgabe**  
  
 Wenn ein Symbol nicht aufgelöst wird, erhalten Sie Informationen über die Funktion durch die folgenden Richtlinien:  
  
 Klicken Sie auf X86 Plattformen, die Aufrufkonvention für ergänzte Namen, die in C kompiliert oder für Extern "C" in C++ wird:  
  
 `__cdecl`  
 Funktion weist einem Unterstrich (_) als Präfix.  
  
 `__stdcall`  
 Funktion hat ein Präfix ein Unterstrich (_) und ein @-Suffix, gefolgt von den Dword ausgerichteten Größe der Parameter auf dem Stapel.  
  
 `__fastcall`  
 Funktion hat ein @-Präfix und ein @-Suffix, gefolgt von den Dword ausgerichteten Größe der Parameter auf dem Stapel.  
  
 Verwenden Sie undname.exe, um die nicht ergänzte Form eines ergänzten Namens zu erhalten.  
  
 Weitere Informationen zu einigen der oben genannten Ursachen finden Sie unter [Namen Dekoration](../../error-messages/tool-errors/name-decoration.md).
