---
title: "Überblick über potenzielle Aktualisierungsprobleme (Visual C++) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c99a8cb-098f-4a9d-bf2c-b80fd06ace43
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f1a727920ffe5e79bd62fd877e191dc6f6f3cc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-potential-upgrade-issues-visual-c"></a>Überblick über potenzielle Aktualisierungsprobleme (Visual C++)
Im Laufe der Jahre wurde der Visual C++-Compiler vielen Änderungen unterzogen, neben Änderungen an der Programmiersprache C++ selbst, an der C++-Standardbibliothek, der C-Laufzeit (CRT) und an anderen Bibliotheken wie MFC und ATL. Daher können beim Aktualisieren einer Anwendung aus einer früheren Version von Visual C++ Compiler- und Linkerfehler sowie Warnungen im Code auftreten, der zuvor ordnungsgemäß kompiliert wurde. Je älter die ursprünglichen Codebasis, desto größer die Wahrscheinlichkeit derartiger Fehler. Diese Übersicht fasst die am häufigsten auftretenden Problemklassen zusammen, mit denen Sie sich wahrscheinlich konfrontiert sehen werden, und enthält Links zu ausführlicheren Informationen.  
  
 Hinweis: In der Vergangenheit haben wir empfohlen, Upgrades, die verschiedene Versionen von Visual Studio umfassen, inkrementell auszuführen, also immer von einer Version zur nächst höheren Version. Dieser Ansatz ist allerdings nicht mehr empfehlenswert. Wir haben festgestellt, dass es fast immer einfacher ist, direkt auf die aktuellste Version von Visual Studio zu aktualisieren, und zwar unabhängig vom Alter der Codebasis.  
  
 Fragen oder Kommentare zum Upgradevorgang können Sie an „vcupgrade(at)microsoft“ senden.  
  
## <a name="library-and-toolset-dependencies"></a>Abhängigkeiten zwischen Bibliothek und Toolset  
 Beim Aktualisieren einer Anwendung auf eine neue Version des Visual C++-Compilers wird dringend empfohlen und in vielen Fällen notwendig, auch alle Bibliotheken und DLLs zu aktualisieren, die mit der Anwendung verknüpft sind. Dies erfordert, dass Sie entweder auf den Quellcode zugreifen können oder dass der Hersteller der Bibliothek Ihnen neue Binärdateien zur Verfügung stellen kann, die mit derselben Hauptversion des Visual C++-Compilers kompiliert wurden. Wenn eine der folgenden Bedingungen zutrifft, können Sie diesen Abschnitt überspringen, der sich mit den Details der Binärdateikompatibilität befasst. Wenn keine der folgenden Bedingungen zutrifft, können die Bibliotheken in Ihrer aktualisierten Anwendung möglicherweise nicht verwendet werden können. Die Informationen in diesem Abschnitt helfen Ihnen zu entscheiden, ob Sie mit der Aktualisierung fortfahren können.  
  
### <a name="toolset"></a>Toolset  
 Die Dateiformate OBJ und LIB sind klar definiert und ändern sich nur selten. Manchmal werden diese Dateiformate erweitert, aber diese Erweiterungen haben im Allgemeinen keinen Einfluss auf die Fähigkeit neuerer Toolsets, die von älteren Toolsets erzeugten Objektdateien und Bibliotheken zu nutzen. Die einzige große Ausnahme hierbei ist die Verwendung von /GL (Link-Zeitcodegenerierung/Optimierung des gesamten Programms) bei der Kompilierung. Wenn Sie mit/GL kompilieren, kann die resultierende Objektdatei nur unter Verwendung desselben Toolsets verknüpft werden, mit dem sie erzeugt wurde. Wurde eine Objektdatei also mit /GL und dem Compiler von Visual Studio 2017 (v141) erzeugt, muss die Verknüpfung mit dem Linker von Visual Studio 2017 (v141) erfolgen. Die Gründe hierfür liegen darin, dass die internen Datenstrukturen innerhalb der /GL-Objekte über Hauptversionen des Toolsets hinweg nicht stabil sind und dass die älteren Datenformate in neueren Toolsets nicht verstanden werden.  
  
 C++ verfügt über keine stabile Anwendungsbinärdatei-Schnittstelle (ABI). Visual C++ verwaltet eine stabile ABI für alle Nebenversionen einer Version. Visual Studio 2017 und alle zugehörigen Updates sind beispielsweise binärkompatibel. Die ABI ist jedoch nicht unbedingt kompatibel über Hauptversionen von Visual C++ hinweg (mit Ausnahme von 2015 und 2017, die _binärkompatibel sind_). Wir können also wichtige Änderungen an C++-Typlayout, Namensergänzung, Ausnahmebehandlung und anderen Teilen der C++-ABI vornehmen. Angenommen, Sie verfügen über eine Objektdatei, die externe Symbole mit C++-Verknüpfung enthält. Dann kann diese Objektdatei möglicherweise nicht ordnungsgemäß mit Objektdateien verknüpft werden, die mit einer anderen Hauptversion des Visual C++-Toolsets erzeugt wurden. Beachten Sie, dass hier „funktioniert möglicherweise nicht“ ganz unterschiedliche Formen annehmen kann: Die Verknüpfung kann vollständig fehlschlagen (z.B. bei geänderter Namensergänzung). Die Verknüpfung kann erfolgreich ausgeführt werden, aber zur Laufzeit treten Fehler auf (z.B. bei geändertem Typlayout). In vielen Fällen funktioniert auch alles fehlerfrei. Beachten Sie außerdem, dass die C++-ABI zwar nicht stabil ist, die C-ABI und die für COM erforderliche Teilmenge der C++-ABI jedoch stabil sind.  
  
### <a name="libraries"></a>Bibliotheken  

 Wenn Sie eine Quelldatei mit einer bestimmten Version der Visual C++-Bibliothekenheader – durch Einschließen (#including) der Header – kompilieren, muss die resultierende Objektdatei mit der gleichen Visual C++-Bibliothekenversion verknüpft werden. Wenn Ihre Quelldatei also mit \<immintrin.h> von Visual Studio 2017 kompiliert wird, müssen Sie eine Verknüpfung zur Visual Studio 2017-Bibliothek „vcruntime“ herstellen. Entsprechend gilt: Wenn Ihre Quelldatei mit \<iostream> von Visual Studio 2017 kompiliert wird, müssen Sie eine Verknüpfung zur C++-Standardbibliothek von Visual Studio 2017 („msvcprt“) herstellen. Das Kombinieren und Anpassen wird nicht unterstützt.  
  
 Für die C++-Standardbibliothek wurde das Kombinieren und Anpassen durch Verwendung von `#pragma detect_mismatch` in den Standardheadern seit Visual Studio 2010 explizit gesperrt. Wenn Sie versuchen, inkompatible Objektdateien zu verknüpfen oder eine Verknüpfung zur falschen Standardbibliothek herzustellen, schlägt die Verknüpfung fehl.  
  
 Für die CRT wurde das Kombinieren und Anpassen nie unterstützt, hat aber oft trotzdem funktioniert, zumindest bis zur Visual Studio 2015-Version und Universal CRT, da die API-Oberfläche bis dahin nicht wesentlich geändert wurde. Mit der Universal CRT wurde die Abwärtskompatibilität unterbrochen, sodass eine Abwärtskompatibilität für die Zukunft erreicht werden kann. Mit anderen Worten, es bestehen keine Pläne, in Zukunft neue Universal CRT-Binärdateien mit Versionsangabe einzuführen. Für die vorhandenen Universal CRT erfolgt jetzt stattdessen eine direkte Aktualisierung.  
  
 Um eine Teilkompatibilität der Verknüpfungen mit Objektdateien (und Bibliotheken) zu gewährleisten, die mit älteren Versionen der Microsoft C-Laufzeitheader kompiliert wurden, stellen wir ab Visual Studio 2015 die Bibliothek „legacy_stdio_definitions.lib“ bereit. Diese Bibliothek bietet Kompatibilitätssymbole für die meisten Funktionen und Datenexporte, die aus der Universal CRT entfernt wurden. Der Satz der von „legacy_stdio_definitions.lib“ bereitgestellten von Kompatibilitätssymbolen reicht aus, um den meisten Abhängigkeiten gerecht zu werden, einschließlich aller Abhängigkeiten in den im Windows SDK enthaltenen Bibliotheken. Es gibt jedoch einige Symbole, die aus der Universal CRT entfernt wurden und für die keine Kompatibilitätssymbole wie diese bereitgestellt werden können. Diese Symbole enthalten einige Funktionen (z.B. \_\_iob\_func) und die Datenexporte (z.B. \_\_imp\_\_\_iob, \_\_imp\_\_\_pctype, \_\_imp\_\_\_mb\_cur\_max).  
  
 Wenn Sie über eine statische Bibliothek verfügen, die mit einer älteren Version der C-Laufzeitheader erstellt wurde, sollten Sie folgende Schritte (in dieser Reihenfolge) ausführen:  
  
1.  Erstellen Sie die statische Bibliothek mithilfe von Visual C++ 2017 und den Universal CRT-Headern neu, um das Verknüpfen mit der Universal CRT zu unterstützen. Dies ist die vollständig unterstützte (und daher beste) Option.  
  
2.  Wenn Sie die statische Bibliothek nicht neu erstellen können (oder möchten), können Sie versuchen, eine Verknüpfung mit „legacy_stdio_definitions.lib“ herzustellen. Wenn damit die Linkzeitabhängigkeiten Ihrer statischen Bibliothek erfüllt sind, sollten Sie die statische Bibliothek in der Form, in der sie in der Binärdatei verwendet wird, gründlich testen, um sicherzustellen, dass sie von den [an der Universal CRT vorgenommenen Änderungen des Verhaltens](visual-cpp-change-history-2003-2015.md#BK_CRT) nicht beeinträchtigt wird.  
  
3.  Wenn die Abhängigkeiten Ihrer statischen Bibliothek durch „legacy_stdio_definitions.lib“ nicht erfüllt werden, oder wenn die Bibliothek mit der Universal CRT aufgrund der oben genannten Änderungen am Verhalten nicht funktioniert, empfehlen wir, die statische Bibliothek in eine DLL zu kapseln, die Sie mit der richtigen Version der Microsoft C-Laufzeit verknüpfen. Wenn die statische Bibliothek beispielsweise mit Visual C++ 2013 erstellt wurde, müssten Sie diese DLL-Datei ebenfalls mit Visual C++ 2013 und den Visual C++-2013-Bibliotheken erstellen. Durch das Erstellen der Bibliothek in einer DLL-Datei kapseln Sie das Implementierungsdetail, das die Abhängigkeit von einer bestimmten Version der Microsoft C-Laufzeit darstellt. (Sie sollten allerdings darauf achten, dass die DLL-Schnittstelle keine Details über die verwendete C-Laufzeit offenlegt, z.B., indem FILE* über die DLL-Grenze hinweg übergeben wird oder indem ein über malloc zugeordneter Zeiger zurückgegeben und vom Aufrufer die Freigabe erwartet wird.)  
  
 Die Verwendung mehrerer CRTs in einem einzigen Prozess ist nicht an und für sich problematisch (tatsächlich werden die meisten Prozesse am Ende mehrere CRT-DLLs laden; Windows-Betriebssystemkomponenten sind z.B. von „msvcrt.dll“ abhängig, und die CLR hängt von ihrer eigenen privaten CRT ab). Probleme entstehen dann, wenn Zustände unterschiedlicher CRTs gemischt werden. Beispielsweise sollten Sie Arbeitsspeicher nicht mit „msvcr110.dll!malloc“ zuweisen und versuchen, die Zuweisung dieses Arbeitsspeichers mit „msvcr120.dll!free“ aufzuheben, und Sie sollten nicht versuchen, eine Datei mit „msvcr110!fopen“ zu öffnen und mit „msvcr120!fread“ daraus zu lesen. Solange Sie die Zustände unterschiedlicher CRTs nicht mischen, können Sie problemlos mehrere CRTs in einem einzigen Prozess laden.  
  
 Weitere Informationen finden Sie unter [Aktualisieren von Code für die Universal CRT](upgrade-your-code-to-the-universal-crt.md).  
  
## <a name="errors-due-to-project-settings"></a>Fehler aufgrund von Projekteinstellungen  
 Um die Aktualisierung zu starten, öffnen Sie einfach ein älteres Projekt, eine ältere Projektmappe bzw. einen älteren Arbeitsbereich in der neuesten Version von Visual Studio. Visual Studio erstellt ein neues Projekt basierend auf den alten Projekteinstellungen. Wenn das ältere Projekt eine Bibliothek oder Pfade enthält, die auf nicht standardmäßige Speicherorte hartcodiert sind, und das Projekt die Standardeinstellungen verwendet, sind die Dateien unter diesen Pfaden für den Compiler möglicherweise nicht sichtbar. Weitere Informationen finden Sie unter [OutputFile-Einstellung des Linkers](porting-guide-spy-increment.md#linker_output_settings).  
  
 Grundsätzlich ist jetzt der ideale Zeitpunkt, Ihren Projektcode richtig zu organisieren, um die Projektwartung zu vereinfachen und die Kompilierung des aktualisierten Codes zu erleichtern und zu beschleunigen. Wenn der Quellcode bereits gut organisiert ist und das ältere Projekt mit Visual Studio 2010 oder höher kompiliert wurde, können Sie die neue Projektdatei manuell bearbeiten, damit die Kompilierung im alten und neuen Compiler unterstützt wird. Das folgende Beispiel zeigt, wie Sie die Kompilierung für Visual Studio 2015 und Visual Studio 2017 durchführen:  
  
```  
<PlatformToolset Condition="'$(VisualStudioVersion)'=='14.0'">v140</PlatformToolset>  
<PlatformToolset Condition="'$(VisualStudioVersion)'=='15.0'">v141</PlatformToolset>   
```  
  
### <a name="lnk2019-unresolved-external"></a>LNK2019: Nicht aufgelöste Externe  
 Für nicht aufgelöste Symbole müssen Sie die Projekteinstellungen möglicherweise korrigieren.  
  
-   Wenn die Quelldatei sich an einem nicht standardmäßigen Speicherort befindet: Haben Sie den Pfad in den „include“-Verzeichnissen des Projekts hinzugefügt?  
  
-   Wenn das externe Symbol in einer LIB-Datei definiert ist: Haben Sie den LIB-Pfad in den Projekteigenschaften angegeben und befindet sich dort tatsächlich die richtige Version der LIB-Datei?  
  
-   Versuchen Sie, eine Verknüpfung zu einer LIB-Datei herzustellen, die mit einer anderen Version von Visual Studio kompiliert wurde? Wenn dies der Fall ist, lesen Sie den vorherigen Abschnitt über Abhängigkeiten zwischen Bibliothek und Toolset.  
  
-   Stimmen die Typen der Argumente an der Aufrufsite tatsächlich mit einer vorhandenen Funktionsüberladung überein? Stellen Sie sicher, dass die zugrunde liegenden Typen für alle Typdefinitionen in der Signatur der Funktion und im Code, der die Funktion aufruft, Ihren Erwartungen entsprechen.  
  
 Um nicht aufgelöste Symbolfehler zu beheben, können Sie mit „dumpbin.exe“ versuchen, die in einer Binärdatei definierten Symbole zu überprüfen. Verwenden Sie zum Anzeigen der in einer Bibliothek definierten Symbole die folgende Befehlszeile:  
  
```  
dumpbin.exe /LINKERMEMBER somelibrary.lib  
```  
  
### <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t ist der systemeigene Typ)  
 (In Visual C++ 6.0 und früher wurde „wchar_t“ nicht als integrierter Typ implementiert, sondern in „wchar.h“ als „typedef“ für „unsigned short“ deklariert.) Der C++-Standard erfordert, dass „wchar_t“ ein integrierter Typ ist. Die Verwendung der „typedef“-Version kann Portabilitätsprobleme verursachen. Wenn Sie ein Upgrade von früheren Visual C++-Versionen durchführen und der Compilerfehler C2664 auftritt, da der Code versucht, „wchar_t“ implizit in „unsigned short“ zu konvertieren, empfiehlt es sich, den Fehler durch eine Codeänderung zu beheben anstatt durch die Einstellung „/Zc:wchar_t-“. Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
### <a name="upgrading-with-the-linker-options-nodefaultlib-entry-and-noentry"></a>Aktualisieren mit den Optionen /NODEFAULTLIB, /ENTRY und /NOENTRY des Linkers  
 Die Linkeroption /NODEFAULTLIB (oder die Linkereigenschaft „Alle Standardbibliotheken ignorieren“) weist den Linker an, in den Standardbibliotheken wie der CRT keine automatische Verknüpfung vorzunehmen. Dies bedeutet, dass jede Bibliothek als einzelne Eingabe aufgelistet werden muss. Diese Liste der Bibliotheken wird in der Eigenschaft „Zusätzliche Abhängigkeiten“ im Linkerabschnitt der Projekteigenschaften angegeben.  
  
 Projekte, die diese Option verwenden, stellen bei der Aktualisierung ein Problem dar, weil die Namen einiger Standardbibliotheken geändert wurden. Da jede Bibliothek in der Eigenschaft „Zusätzliche Abhängigkeiten“ oder in der Befehlszeile des Linkers aufgelistet werden muss, ist es erforderlich, die Liste der Bibliotheken so zu aktualisieren, dass die aktuellen Namen verwendet werden.  
  
 Die folgende Tabelle zeigt die Bibliotheken, deren Namen seit Visual Studio 2015 geändert wurden. Zum Aktualisieren müssen Sie die Namen in der ersten Spalte durch die Namen in der zweiten Spalte ersetzen.  Einige dieser Bibliotheken sind Importbibliotheken, das sollte aber keine Rolle spielen.  
  
|||  
|-|-|  
|Bisher verwendet:|Zu ersetzen durch:|  
|libcmt.lib|libucrt.lib, libvcruntime.lib|  
|libcmtd.lib|libucrtd.lib, libvcruntimed.lib|  
|msvcrt.lib|ucrt.lib, vcruntime.lib|  
|msvcrtd.lib|ucrtd.lib, vcruntimed.lib|  
  
 Dasselbe Problem tritt auch auf, wenn Sie die Option /ENTRY oder die Option /NOENTRY verwenden, die ebenfalls zur Umgehung der Standardbibliotheken führen.  
  
## <a name="errors-due-to-improved-language-conformance"></a>Fehler aufgrund der verbesserten Sprachübereinstimmung  
 Die Übereinstimmung des Visual C++-Compilers mit dem C++-Standard wurde über die Laufe fortlaufend verbessert. Code, der in früheren Versionen von Visual C++ kompiliert wurde, lässt sich in Visual Studio 2017 möglicherweise nicht kompilieren, weil der Compiler einen Fehler ordnungsgemäß kennzeichnet, der zuvor ignoriert wurde oder explizit erlaubt war.  
  
 Der Schalter „/Zc: forScope“ wurde beispielsweise früh im Verlauf von Visual C++ eingeführt. Er lässt nicht konformes Verhalten für Schleifenvariablen zu. Dieser Schalter ist inzwischen veraltet und kann in zukünftigen Versionen entfernt werden. Es wird dringend empfohlen, diesen Schalter nicht zu verwenden, wenn Sie Code aktualisieren. Weitere Informationen finden Sie unter [/Zc:forScope- ist veraltet](porting-guide-spy-increment.md#deprecated_forscope).  
  
 Ein Beispiel für einen bei der Aktualisierung häufig auftretenden Compilerfehler ist die Übergabe eines nicht konstanten Arguments an einen konstanten Parameter. Ältere Versionen von Visual C++ haben dies nicht immer als Fehler gekennzeichnet. Weitere Informationen finden Sie unter [Strikte Compilerkonvertierungen](porting-guide-spy-increment.md#stricter_conversions).  
  
 Weitere Informationen zu bestimmten Verbesserungen an der Übereinstimmung mit Standards finden Sie unter [Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md) und [Verbesserungen an C++ bei der Übereinstimmung in Visual Studio 2017](../cpp-conformance-improvements-2017.md).  
  
## <a name="errors-involving-stdinth-integral-types"></a>Fehler im Zusammenhang mit ganzzahligen \<stdint.h>-Typen  
 Der Header \<stdint.h> definiert Typdefinitionen und Makros, die im Gegensatz zu integrierten ganzzahligen Typen auf allen Plattformen garantiert über eine festgelegte Länge verfügen. Beispiele hierfür sind „uint32_t“ und „int64_t“. Visual C++ hat \<stdint.h> in Visual Studio 2010 hinzugefügt. Code, der vor 2010 geschrieben wurde, stellte möglicherweise private Definitionen für diese Typen bereit, und diese Definitionen sind nicht immer mit den \<stdint.h>-Definitionen konsistent.  
  
 Wenn der Fehler C2371 generiert wird, und ein „stdint“-Typ beteiligt ist, bedeutet dies wahrscheinlich, dass der Typ in einem Header entweder im Code oder in der LIB-Datei eines Drittanbieters definiert ist.  Bei der Aktualisierung sollten Sie alle benutzerdefinierten Definitionen des Typs \<stdint.h> vermeiden. Vergleichen Sie jedoch zuerst die benutzerdefinierten Definitionen mit den Definitionen des aktuellen Standards, um sicherzustellen, dass keine neuen Probleme entstehen.  
  
 Mit F12 **Gehe zu Definition** können Sie anzeigen, wo der betreffende Typ definiert ist.  
  
 Die Compileroption [/showIncludes](../build/reference/showincludes-list-include-files.md) kann hier hilfreich sein. Öffnen Sie im Dialogfeld „Eigenschaftenseiten“ für Ihr Projekt die Seite **C/C++**, **Erweitert**, und legen Sie **Includes anzeigen** auf **Ja** fest. Erstellen Sie das Projekt anschließend neu, und schauen Sie sich die Liste der #includes im Ausgabefenster an.  Jeder Header wird unterhalb des Headers, der ihn enthält, eingerückt.  
  
## <a name="errors-involving-crt-functions"></a>Fehler im Zusammenhang mit CRT-Funktionen  
 Im Laufe der Jahre wurden viele Änderungen an der C-Laufzeit vorgenommen. Viele sichere Versionen von Funktionen wurden hinzugefügt, und einige Funktionen wurden entfernt. Darüber hinaus wurde, wie oben in diesem Artikel beschrieben, die Microsoft-Implementierung der CRT in Visual Studio 2015 in neue Binärdateien und zugehörigen LIB-Dateien umgestaltet.  
  
 Wenn ein Fehler eine CRT-Funktion betrifft, suchen Sie in den Artikeln [Wichtige Änderungen in Visual C++ 2003-2015](visual-cpp-change-history-2003-2015.md) oder [Verbesserungen an der Übereinstimmung mit Standards in Visual C++ in Visual Studio 2017](../cpp-conformance-improvements-2017.md) nach zusätzlichen Informationen. Wenn der Fehler „LNK2019, Nicht aufgelöste Externe“ auftritt, stellen Sie sicher, dass die Funktion nicht entfernt wurde. Wenn Sie jedoch sicher sind, dass die Funktion noch vorhanden und der aufrufende Codes korrekt ist, überprüfen Sie, ob im Projekt /NODEFAULTLIB verwendet wird. Ist dies der Fall, müssen Sie die Liste der Bibliotheken aktualisieren, sodass das Projekt die neuen universellen Bibliotheken (UCRT) verwendet. Weitere Informationen finden Sie oben im Abschnitt zu Bibliotheken und Abhängigkeiten.  
  
 Wenn der Fehler „printf“ oder „scanf“ betrifft, stellen Sie sicher, dass Sie die beiden Funktion nicht privat und ohne „stdio.h“ definieren. Ist dies der Fall, entfernen Sie die privaten Definitionen oder stellen Sie eine Verknüpfung mit „legacy_stdio_definitions.lib“ (Projekt &#124; Eigenschaften &#124; Linker &#124; Linkereingabe) her. Wenn Sie eine Verknüpfung mit Windows SDK 8.1 oder früher herstellen, fügen Sie „legacy_stdio_definitions.lib“ hinzu.  
  
 Wenn der Fehler Argumente von Formatzeichenfolgen betrifft, liegt die Ursache wahrscheinlich darin, dass der Compiler eine strengere Erzwingung als der Standard einsetzt. Weitere Informationen finden Sie im Änderungsverlauf. Bitte berücksichtigen Sie alle hier aufgeführten Fehler, da sie ein potenzielles Sicherheitsrisiko darstellen.  
  
## <a name="errors-due-to-changes-in-the-c-standard"></a>Fehler aufgrund von Änderungen im C++-Standard  
 Der C++-Standard selbst hat sich auf eine Art und Weise entwickelt, die nicht immer abwärts kompatibel ist. Die Einführung von Verschiebesemantik, neuen Schlüsselwörtern sowie anderen Sprach- und Standardbibliothekfeatures in C ++11 kann potenziell Compilerfehler und sogar ein unterschiedliches Laufzeitverhalten verursachen.  
  
 Ein altes C++-Programm kann z. B. den „iostream.h“-Header enthalten. Dieser Header ist im Verlauf von C++ schon lange veraltet, und wurde aus Visual C++ schließlich vollständig entfernt. Sie müssen in diesem Fall \<iostream> verwenden und Ihren Code neu schreiben. Weitere Informationen finden Sie unter [Aktualisieren von altem iostreams-Code](porting-guide-spy-increment.md#updating_iostreams_code).  
  
### <a name="c4838-narrowing-conversion-warning"></a>Warnung „C4838: Einschränkende Konvertierung“  
 Der C++-Standard legt jetzt fest, dass Konvertierungen von ganzzahligen Werten ohne Vorzeichen in ganzzahlige Werte mit Vorzeichen als einschränkende Konvertierungen angesehen werden. Der Visual C++-Compiler hat diese Warnung vor Visual Studio 2015 nicht ausgelöst. Sie sollten jedes Vorkommen überprüfen, um sicherzustellen, dass die Richtigkeit Ihres Codes durch diese Einschränkung nicht beeinträchtigt wird.  
  
## <a name="warnings-to-use-secure-crt-functions"></a>Warnungen zur Verwendung von sicheren CRT-Funktionen  
 Im Laufe der Jahre wurden sichere Versionen der C-Laufzeitfunktionen eingeführt. Die alten, nicht sicheren Versionen sind zwar weiterhin verfügbar, sie sollten Ihren Code jedoch ändern und die sicheren Versionen verwenden. Der Compiler gibt bei Verwendung der nicht sicheren Versionen eine Warnung aus. Sie können diese Warnungen auch deaktivieren oder ignorieren. Um die Warnung für alle Projekte in der Projektmappe zu deaktivieren, öffnen Sie **Ansicht &#124; Eigenschaften-Manager**, wählen Sie alle Projekte aus, für die Sie die Warnung deaktivieren möchten, klicken Sie dann mit der rechten Maustaste auf die ausgewählten Elemente, und wählen Sie **Eigenschaften &#124; C/C++ &#124; Erweitert &#124; Bestimmte Warnungen deaktivieren** aus. Klicken Sie auf den Dropdownpfeil, und klicken Sie dann auf „Bearbeiten“. Geben Sie „4996“ in das Textfeld ein (ohne das Präfix „C“). Weitere Informationen finden Sie unter [Portierung zur Verwendung der sicheren CRT](porting-guide-spy-increment.md#porting_to_secure_crt).  
  
## <a name="errors-due-to-changes-in-windows-apis-or-obsolete-sdks"></a>Fehler aufgrund von Änderungen in Windows-APIs oder veralteten SDKs  
 Im Laufe der Jahre wurden Windows-APIs und Datentypen hinzugefügt sowie manchmal geändert oder entfernt. Darüber hinaus wurden andere SDKs, die nicht zum Kernbetriebssystem gehörten, hinzugefügt und entfernt. Ältere Programme können daher Aufrufe von APIs enthalten, die nicht mehr vorhanden sind. Sie können auch Aufrufe von APIs in anderen Microsoft-SDKs enthalten, die nicht mehr unterstützt werden.  Wenn einen Fehler im Zusammenhang mit einer Windows-API oder einer API aus einem älteren Microsoft-SDK angezeigt wird, ist es möglich, dass eine API entfernt bzw. von einer neueren, sichereren Funktion abgelöst wurde.  
  
 Weitere Informationen zum aktuellen API-Satz und den Mindestversionen der unterstützten Betriebssysteme für eine bestimmte Windows-API finden Sie unter [Index der Windows-APIs](https://msdn.microsoft.com/en-us/library/ff818516\(v=vs.85\).aspx) unter der betreffenden API.  
  
### <a name="windows-version"></a>Windows-Version  
 Beim Aktualisieren eines Programms, das die Windows-API direkt oder indirekt verwendet, müssen Sie entscheiden, welche Mindestversion von Windows unterstützt werden soll. In den meisten Fällen ist Windows 7 eine gute Wahl. Weitere Informationen finden Sie unter [Probleme mit Headerdateien](porting-guide-spy-increment.md#header_file_problems). Das Makro WINVER definiert die älteste Version von Windows, unter der das Programm ausgeführt werden kann. Wenn Ihr MFC-Programm WINVER auf 0x0501 (Windows XP) festlegt, wird eine Warnung angezeigt, da XP von MFC nicht mehr unterstützt wird, obwohl der Compiler selbst über einen XP-Modus verfügt.  
  
 Weitere Informationen finden Sie unter [Aktualisieren der Windows-Zielversion](porting-guide-spy-increment.md#updating_winver) und [Weitere veraltete Headerdateien](porting-guide-spy-increment.md#outdated_header_files).  
  
## <a name="atl--mfc"></a>ATL/MFC  
 ATL und MFC sind relativ stabile APIs, allerdings werden auch hier gelegentlich Änderungen vorgenommen. Weitere Informationen finden Sie unter [Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md) sowie [Neues bei Visual C++ in Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md) und [Verbesserungen an C++ bei der Übereinstimmung in Visual Studio 2017](../cpp-conformance-improvements-2017.md).  
  
### <a name="lnk-2005-dllmain12-already-defined-in-msvcrtdlib"></a>LNK 2005 _DllMain@12 wurde bereits in „MSVCRTD.lib“ definiert  
 Dieser Fehler kann in MFC-Anwendungen auftreten. Er weist auf ein Sortierungsproblem zwischen der CRT- und der MFC-Bibliothek hin. MFC muss zuerst so verknüpft werden, dass die Operatoren „new“ und „delete“ bereitgestellt werden. Um den Fehler zu beheben, verwenden Sie den Schalter/NODEFAULTLIB, um diese Standardbibliotheken zu ignorieren: „MSVCRTD.lib“ und „mfcs140d.lib“. Fügen Sie diese Bibliotheken dann als zusätzliche Abhängigkeiten hinzu.  
  
## <a name="32-vs-64-bit"></a>32-Bit oder 64-Bit  
 Wenn Ihr ursprünglicher Code für 32-Bit-Systeme kompiliert wurde, können Sie eine 64-Bit-Version anstelle von oder zusätzlich zu einer neuen 32-Bit-App erstellen. Im Allgemeinen sollten Sie das Programm zuerst im 32-Bit-Modus kompilieren, und anschließend die Kompilierung der 64-Bit-Version vornehmen. Die Kompilierung für 64-Bit ist einfach, aber in einigen Fällen werden Fehler sichtbar, die in 32-Bit-Builds verborgen waren.  
  
 Außerdem sollten Sie mögliche Probleme im Zusammenhang mit Zeigergröße, Zeit- und Größenwerten sowie Formatbezeichnern in den Funktionen „printf“ und „scanf“ kennen, die während der Kompilierung und zur Laufzeit auftreten können. Weitere Informationen finden Sie unter [Konfigurieren von Visual C++ für für 64-Bit-x64-Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md) und [Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++](../build/common-visual-cpp-64-bit-migration-issues.md). Weitere Migrationstipps finden Sie im [Programmierhandbuch für 64-Bit-Windows](https://msdn.microsoft.com/library/windows/desktop/bb427430\(v=vs.85\).aspx).  
  
## <a name="unicode-vs-mbcsascii"></a>Unicode oder MBCS/ASCII  
 Bevor Unicode standardisiert wurde, verwendeten viele Programme den Mehrbyte-Zeichensatz (MBCS) zur Darstellung von Zeichen, die im ASCII-Zeichensatz nicht enthalten sind. In älteren MFC-Projekten war der MBCS die Standardeinstellung, und wenn Sie ein solches Programm aktualisieren, werden Warnungen angezeigt, die Ihnen raten, stattdessen Unicode zu verwenden. Sie können die Warnung deaktivieren oder ignorieren, wenn Sie entscheiden, dass die Konvertierung in Unicode die Entwicklungskosten nicht wert ist. Um die Warnung für alle Projekte in der Projektmappe zu deaktivieren, öffnen Sie **Ansicht &#124; Eigenschaften-Manager**, wählen Sie alle Projekte aus, für die Sie die Warnung deaktivieren möchten, klicken Sie dann mit der rechten Maustaste auf die ausgewählten Elemente, und wählen Sie **Eigenschaften &#124; C/C++ &#124; Erweitert &#124; Bestimmte Warnungen deaktivieren** aus. Klicken Sie auf den Dropdownpfeil, und klicken Sie dann auf „Bearbeiten“. Geben Sie „4996“ in das Textfeld ein (ohne das Präfix „C“).  
  
 Weitere Informationen finden Sie unter [Portieren von MBCS zu Unicode](porting-guide-spy-increment.md#porting_to_unicode). Allgemeine Informationen zu MBCS im Vergleich zu Unicode finden Sie unter [Text und Zeichenfolgen in Visual C++](../text/text-and-strings-in-visual-cpp.md) und [Internationalisierung](../c-runtime-library/internationalization.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktualisieren von Projekten von früheren Versionen von Visual C++](upgrading-projects-from-earlier-versions-of-visual-cpp.md) [Verbesserungen an C++ bei der Übereinstimmung in Visual Studio 2017](../cpp-conformance-improvements-2017.md)
