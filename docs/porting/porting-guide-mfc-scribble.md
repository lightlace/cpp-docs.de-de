---
title: "Leitfaden zum Portieren: MFC Scribble | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Leitfaden zum Portieren: MFC Scribble
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema ist das erste von mehreren Themen, in denen der Aktualisierungsvorgang für Visual C\+\+\-Projekte vorgestellt wird, die in älteren Versionen von Visual Studio erstellt wurden, auf [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)].  Diese Themen stellen den Aktualisierungsvorgang durch Beispiele vor, beginnend mit einem sehr einfachen Projekt, um danach mit etwas komplexeren fortzufahren.  In diesem Abschnitt arbeiten wir uns durch den Aktualisierungsvorgang für ein bestimmtes Projekt, MFC Scribble.  Es eignet sich als grundlegende Einführung in den Aktualisierungsvorgang für C\+\+\-Projekte.  
  
 In jeder Version von Visual Studio gibt es mögliche Inkompatibilitäten, die das Verschieben von Code aus einer älteren Version von Visual Studio in eine neuere erschweren können.  Manchmal sind die erforderlichen Änderungen im Code, sodass Sie den Code erneut kompilieren und aktualisieren müssen, und manchmal betreffen die erforderlichen Änderungen die Projektdateien.  Wenn Sie ein Projekt öffnen, das mit einer früheren Version von Visual Studio erstellt wurde, fragt Sie Visual Studio automatisch, ob ein Projekt oder eine Projektmappe auf die neueste Version aktualisiert werden soll.  Diese Tools aktualisieren in der Regel nur die Projektdateien. Sie ändern nicht den Quellcode.  
  
## MFC Scribble  
 MFC Scribble ist ein bekanntes Beispiel, das in vielen verschiedenen Versionen von Visual C\+\+ eingeschlossen wurde.  Es handelt sich dabei um eine einfache Zeichenanwendung, die einige der grundlegenden Funktionen von MFC veranschaulicht.  Es gibt davon verschiedene Versionen, u. a. in verwaltetem und systemeigenem Code.  In diesem Beispiel haben wir eine alte Version von Scribble in systemeigenem Code aus Visual Studio 2005 gefunden und in [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] geöffnet.  
  
 Vor dem Aktualisierungsversuch sichern wir die gesamte Lösung und den gesamten Inhalt.  Danach wählen wir die spezielle Aktualisierungsmethode aus.  Für komplexere Lösungen und Projekte, die für längere Zeit nicht aktualisiert wurden, sollten Sie möglicherweise jeweils nur eine Version von Visual Studio gleichzeitig aktualisieren.  Auf diese Weise können Sie eingrenzen, welche Version von Visual Studio ein Problem verursacht hat.  Ein einfaches Projekt können Sie es in der aktuellen Version von Visual Studio öffnen und zulassen, dass der Assistent das Projekt konvertiert.  Wenn dies nicht funktioniert, können Sie versuchen, jeweils nur eine Version zu aktualisieren, wenn Sie Zugriff auf die entsprechenden Versionen von Visual Studio haben.  
  
 Beachten Sie, dass Sie devenv auch in der Befehlszeile mithilfe der `/Upgrade`\-Option ausführen können, anstatt den Assistenten zum Aktualisieren von Projekten zu verwenden.  Siehe [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md).  Das kann hilfreich bei der Automatisierung des Aktualisierungsvorgangs für eine große Anzahl von Projekten sein.  
  
### Schritt 1.Konvertieren der Projektdatei  
 Wenn Sie eine alte Projektdatei in Visual Studio 2015 öffnen, bietet Visual Studio das Konvertieren der Projektdatei in die aktuelle Version, was wir akzeptiert haben.  Das folgende Dialogfeld wurde angezeigt:  
  
 ![Projekt&#45; und Projektmappenänderungen überprüfen](../porting/media/scribbleprojectupgrade.png "ScribbleProjectUpgrade")  
  
 Es ist ein Fehler aufgetreten, der uns darüber informiert, dass das Itanium\-Ziel nicht verfügbar ist und nicht konvertiert wird.  
  
  **Die Plattform „Itanium“ fehlt in diesem Projekt.  Alle speziellen Konfigurationen und ihre Dateikonfigurationseinstellungen für diese Plattform werden ignoriert.  Wenn diese Plattform konvertiert werden soll, stellen Sie sicher, dass die entsprechende Plattform unter „%vctargetpath%\\platforms\\Itanium“ installiert ist.  Mit der Konvertierung dieses Projekts ohne diese Plattform fortfahren?**  Zu dem Zeitpunkt, als das vorherige Scribble\-Projekt erstellt wurde, war Itanium eine wichtige Zielplattform.  Die Windows\-Plattform unterstützt Itanium nicht mehr, daher wählen wir aus, ohne Unterstützung der Itanium\-Plattform fortzufahren.  
  
 Visual Studio hat dann einen Migrationsbericht mit einer Liste aller Probleme der alten Projektdatei angezeigt.  
  
 ![Upgradebericht](../porting/media/scribblemigrationreport.png "ScribbleMigrationReport")  
  
 In diesem Fall waren alle Probleme Warnungen, und Visual Studio hat die entsprechenden Änderungen in der Projektdatei vorgenommen.  Der große Unterschied hinsichtlich des Projekts liegt darin, dass das Buildtool von vcbuild in msbuild geändert wurde.  Diese Änderung wurde in Visual Studio 2010 eingeführt.  Weitere Änderungen umfassen u. a. eine Neuanordnung der Elementreihenfolge in der Projektdatei selbst.  Keines der Probleme bedurfte für dieses einfache Projekt weiterer Aufmerksamkeit.  
  
### Schritt 2.Erstellen des Projekts  
 Vor der Erstellung überprüfen wir das Plattformtoolset, damit wir wissen, welche Compilerversion das Projektsystem verwendet.  Sehen Sie sich im Dialogfeld für Projekteigenschaften unter **Konfigurationseigenschaften** in der Kategorie **Allgemein** die Eigenschaft **Plattformtoolset** an.  Sie enthält die Version von Visual Studio und die Versionsnummer des Plattformtools, in diesem Fall v140 für die Version [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] der Tools.  Wenn Sie ein Projekt konvertieren, das ursprünglich mit Visual C\+\+ 2010, 2012 oder 2013 kompiliert wurde, wird das Toolset nicht automatisch auf das [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]\-Toolset aktualisiert.  Im Fall von Scribble wurde die Version, die wir konvertiert haben, für Visual Studio 2005 erstellt, sodass sie für die Verwendung des neuesten Toolsets konvertiert wird.  
  
 Beim Erstellen tritt das erste Problem aufgrund des MBCS\-Codes auf.  
  
  **Fehler MSB8031:**  Der Link in der Fehlermeldung führt zu einem Thema zum Veralten von MBCS in Visual Studio 2013.  Standardmäßig umfassen die MFC\-Installation in Visual C\+\+ 2013 nicht die MBCS\-Version von MFC.  Die MBCS\-Version von MFC ist erforderlich, um dieses Projekt in seiner aktuellen Form zu erstellen.  Wir können den Code zum Verwenden von Unicode migrieren, oder wir können die MBCS\-Version von MFC herunterladen und installieren.  Wenn wir die MBCS\-Version von MFC herunterladen, können wir eine Definition für das Makro NO\_WARN\_MBCS\_MFC\_DEPRECATION hinzufügen, um diese Warnung zu unterdrücken.  
  
 Informationen zum Herunterladen der MBCS\-Version von MFC und zum Veralten der MBCS\-Version von MFC finden Sie im Artikel [MFC MBCS DLL\-Add\-On](../mfc/mfc-mbcs-dll-add-on.md) und im VC\-Blog. Laden Sie die MBCS\-Version von MFC [hier](http://www.microsoft.com/download/details.aspx?id=44930) herunter.  Fügen Sie im Dialogfeld für Projekteigenschaften unter der Kategorie **C\/C\+\+** unter **Präprozessor** das Makro NO\_WARN\_MBCS\_MFC\_DEPRECATION zur Liste der vordefinierten Makros hinzu.  
  
 Für den Wechsel zu Unicode öffnen Sie die Projekteigenschaften unter **Konfigurationseigenschaften**, wählen Sie den Abschnitt **Allgemein** aus, und suchen Sie die **Zeichensatz**\-Eigenschaft.  Ändern Sie sie von **Multibyte\-Zeichensatz verwenden** in **Unicode\-Zeichensatz verwenden**.  Als Effekt dieser Änderung sind jetzt die Makros \_UNICODE und UNICODE definiert, \_MBCS aber nicht, was Sie im Eigenschaftendialogfeld unter der Kategorie **C\/C\+\+** der **Befehlszeile**\-Eigenschaft überprüfen können.  
  
  **\/GS \/analyze\- \/W4 \/Gy \/Zc:wchar\_t \/Zi \/Gm\- \/O2 \/Ob1 \/Fd".  \\Release\\vc140.pdb" \/Zc:inline \/fp:precise \/D "\_AFXDLL" \/D "WIN32" \/D "NDEBUG" \/D "\_WINDOWS" \/D "\_UNICODE" \/D "UNICODE" \/errorReport:prompt \/GF \/WX \/Zc:forScope \/Gd \/Oy \/MD \/Fa".  \\Release\\" \/EHsc \/nologo \/Fo".  \\Release\\" \/Fp".  \\Release\\Scribble.pch"**  Obwohl das Scribble\-Projekt nicht für die Kompilierung mit Unicode\-Zeichen eingerichtet wurde, wurde es bereits mit TCHAR anstelle von char geschrieben, sodass nichts tatsächlich geändert werden muss.  Das Projekt wird erfolgreich mit dem Unicode\-Zeichensatz erstellt.  
  
 Es gibt aber ein anderes Problem.  Der Compiler gibt in etwa folgendermaßen an, dass \_WINNT32\_WINNT nicht definiert ist:  
  
  **\_WIN32\_WINNT nicht definiert.  Es wird \_WIN32\_WINNT\_MAXVER verwendet \(siehe WinSDKVer.h\)**  Dies ist eine Warnung, kein Fehler, und kommt sehr häufig vor, wenn ein Visual C\+\+\-Projekt aktualisiert wird.  Dies ist das Makro, das die niedrigste Version von Windows definiert, auf der Ihre Anwendung ausgeführt werden kann.  Wenn wir die Warnung ignorieren, akzeptieren wir den Standardwert \_WIN32\_WINNT\_MAXVER, d. h. die aktuelle Version von Windows.  Eine Tabelle der möglichen Werte finden Sie unter [Verwenden der Windows\-Header](https://msdn.microsoft.com/de-de/library/aa383745.aspx).  Beispielsweise können wir ihre Ausführung auf eine beliebige Version ab Vista festlegen.  
  
```  
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
 Wenn der Code Teile der Windows\-API verwendet, die nicht in der Version von Windows verfügbar sind, die Sie mit diesem Makro angeben, sollte das als Compilerfehler angezeigt werden.  Im Fall des Scribble\-Codes gibt es keinen Fehler.  
  
### Schritt 3.Testen und Debuggen  
 Es gibt keine Testsammlung, daher haben wir die App einfach gestartet und ihre Funktionen manuell über die Benutzeroberfläche getestet.  Es wurden keine Probleme festgestellt.  
  
### Schritt 4.Verbessern des Codes  
 Da Sie jetzt auf Visual Studio 2015 migriert haben, möchten Sie u. U. einige Änderungen vornehmen, um die neuen C\+\+\-Features zu nutzen.  Die aktuelle Version des Visual C\+\+\-Compilers entspricht viel mehr dem C\+\+\-Standard als ältere Versionen. Wenn Sie also Codeänderungen vornehmen möchten, um den Code sicherer und besser portierbar für andere Compiler und Betriebssysteme zu machen, sollten Sie einige Verbesserungen vornehmen.  
  
## Nächste Schritte  
 Scribble war eine kleine und einfache Windows\-Desktopanwendung, bei der Konvertierungen einfach waren.  Viele kleine, einfache Anwendungen können genauso einfach in die neue Version konvertiert werden.  Für komplexere Anwendungen mit viel mehr Codezeilen, für älteren Legacycode, der möglicherweise nicht den modernen technischen Standards entspricht, für mehrere Projekte und Bibliotheken, benutzerdefinierte Buildschritte oder für komplexe geskriptete automatische Builds ist die Aktualisierung zeitaufwendiger.  Fahren Sie mit dem [nächsten Beispiel](../porting/porting-guide-com-spy.md) fort, eine ATL\/COM\-Anwendung, die COM Spy genannt wird.  
  
## Siehe auch  
 [Portieren und Aktualisieren: Beispiele und Fallstudien](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Nächstes Beispiel: COM Spy](../porting/porting-guide-com-spy.md)