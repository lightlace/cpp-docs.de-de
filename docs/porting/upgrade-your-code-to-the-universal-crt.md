---
title: Upgraden Ihres Codes auf die Universal CRT
ms.date: 03/31/2017
ms.assetid: eaf34c1b-da98-4058-a059-a10db693a5ce
ms.openlocfilehash: ba987c6c88a3b559b8fe6224fd27dfbfe8c9d821
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741334"
---
# <a name="upgrade-your-code-to-the-universal-crt"></a>Upgraden Ihres Codes auf die Universal CRT

In Visual Studio 2015 wurde die Microsoft C-Laufzeitbibliothek (C Runtime Library, CRT) umgestaltet. Die C-Standardbibliothek, POSIX-Erweiterungen und Microsoft-spezifische Funktionen, Makros sowie globale Variablen wurden in eine neue Bibliothek verschoben, die universelle C-Laufzeitbibliothek (universelle CRT oder UCRT). Die compilerspezifischen Komponenten der CRT wurden in eine neue vcruntime-Bibliothek verschoben.

Die UCRT ist nun eine Windows-Komponente und wird als Bestandteil von Windows 10 bereitgestellt. Die UCRT unterstützt eine stabile ABI, die auf C-Aufrufkonvention basiert und den Standard ISO C99 (mit nur wenigen Ausnahmen) erfüllt. Sie ist nicht länger an eine bestimmte Version des Compilers gebunden. Sie können die UCRT unter jeder Version von Windows verwenden, die von Visual Studio 2015 oder Visual Studio 2017 unterstützt wird. Der Vorteil ist, dass Sie nicht länger Ihre Builds aktualisieren müssen, um auf eine Version der CRT mit jedem Visual Studio-Upgrade abzuzielen.

Mit dieser Umgestaltung haben sich die Namen oder Orte vieler CRT-Headerdateien, Bibliotheksdateien und verteilbaren Dateien sowie die von Ihrem Code erforderlichen Bereitstellungsmethoden verändert. Darüber hinaus wurden viele Funktionen und Makros in der UCRT zur Verbesserung der Einhaltung von Standards hinzugefügt oder geändert. Um von diesen Änderungen zu profitieren, müssen Ihr vorhandener Code und Ihre Projekterstellungssysteme aktualisiert werden.

## <a name="where-to-find-the-universal-crt-files"></a>Wo die universellen CRT-Dateien zu finden sind

Als Windows-Komponente sind die UCRT-Bibliotheksdateien und -header nun Teil des Windows Software Development Kit (SDK). Wenn Sie Visual Studio installieren, werden Teile des Windows SDK auch installiert, die zur Verwendung der UCRT erforderlich sind. Der Visual Studio-Installer fügt die Speicherorte der UCRT-Header, -Bibliotheken und -DLL-Dateien zu den Standardpfaden hinzu, die vom Projekterstellungssystem von Visual Studio verwendet werden. Wenn Sie Ihre Visual C++-Projekte aktualisieren und diese die Standardprojekteinstellungen verwenden, findet die IDE automatisch neue Speicherorte für die Headerdateien, und der Linker verwendet automatisch die neue Standard-UCRT und vcruntime-Bibliotheken. Ebenso werden die Umgebungsvariablen, die Pfade für Header und Bibliotheken enthalten, aktualisiert und arbeiten auch automatisch, wenn Sie die Developer-Eingabeaufforderung verwenden, um die Funktion „Erstellen über die Befehlszeile“ zu nutzen.

Die Headerdateien der C-Standardbibliothek befinden sich nun im Windows SDK in einem Includeordner in einem der Version des SDK spezifischen Verzeichnis. Ein typischer Speicherort für die Headerdateien ist im Verzeichnis „Programme“ oder „Programme (x86)“ unter „Windows-Kits\\10\\Einschließen\\_SDK-Version_\\UCRT“, wobei _SDK-Version_ einer Windows-Version oder einem Update entspricht, z.B. 10.0.14393.0 für das Anniversary-Update von Windows 10.

Die statischen UCRT-Bibliotheken und Stub-DLLs befinden sich im Verzeichnis „Programme“ oder „Programme (x86)“ unter „Windows-Kits\\10\\Lib\\_SDK-Version_\\UCRT\\_architecture_“, wobei _architecture_ ARM, x86 oder X64 ist. Die Retail- und Debug-Bibliotheken sind „libucrt.lib“ und „libucrtd.lib“ und die Bibliotheken für die UCRT-DLLs sind „ucrt.lib“ und „ucrtd.lib“.

Die eigentlichen UCRT-DLLs und diejenigen zum Debuggen befinden sich an anderen Speicherorten. Retail-DLLs sind weiterverteilbar. Sie finden sie unter „Programme“ oder „Programme (x86)“ unter „Windows-Kits\\10\\redist\\ucrt\\DLLs\\_architecture_\.“. UCRT-Debugbibliotheken sind nicht weiterverteilbar. Sie finden sie unter „Programme“ oder „Programme (x86)“ im Ordner „Windows-Kits\\10\\bin\\_architecture_\\ucrt“.

Der compilerspezifische C- und C++Unterstützungsbibliothek für die Laufzeit, **vcruntime**, enthält den erforderlichen Code für die Unterstützung des Programmstarts und Features wie die Ausnahmebehandlung und Interna. Die Bibliothek und deren Headerdateien befinden sich noch immer im versionsspezifischen Microsoft Visual Studio-Ordner in Ihrem Verzeichnis „Programme“ oder „Programme (x86)“. In Visual Studio 2017 befinden sich die Header unter „Microsoft Visual Studio\\2017\\_edition_\\VC\\Tools\\MSVC\\_lib-version_\\include (Einschließen)“, und die Link Libraries befinden sich unter „Microsoft Visual Studio\\2017\\_edition_\\VC\\Tools\\MSVC\\_lib-version_\\lib\\_architecture_“, wobei _edition_ die Edition der installierten Visual Studio-Version ist. _lib-version_ ist die Version der Bibliotheken und _architecture_ ist die Prozessorarchitektur. Link Libraries für OneCore und Store sind auch im Bibliotheksordner vorhanden. Die Retail- und Debugversionen der statischen Bibliothek sind „libvcruntime.lib“ und „libvcruntimed.lib“. Die Retail- und Debug-Stub-Bibliotheken der dynamischen Verknüpfung sind jeweils „vcruntime.lib“ und „vcruntimed.lib“.

Wenn Sie Ihre Visual C++-Projekte aktualisieren und Sie die **Linker** -Eigenschaft **Alle Standardbibliotheken ignorieren** des Projekts auf **Ja** festgelegt haben oder die Linkeroption `/NODEFAULTLIB` in der Befehlszeile verwenden, müssen Sie die Liste der Bibliotheken so aktualisieren, dass sie die neuen umgestalteten Bibliotheken enthält. Ersetzen Sie die alte CRT-Bibliothek (z.B. libcmt.lib, libcmtd.lib, msvcrt.lib oder msvcrtd.lib) mit den entsprechenden umgestalteten Bibliotheken. Informationen zu den bestimmten Bibliotheken, die Sie verwenden können, finden Sie unter [CRT Library Features (Features der CRT-Bibliothek)](../c-runtime-library/crt-library-features.md).

## <a name="deployment-and-redistribution-of-the-universal-crt"></a>Bereitstellung und Neuverteilung der Universal CRT

Da die UCRT jetzt eine Komponente des Betriebssystems Microsoft Windows ist, ist sie als Teil des Betriebssystems in Windows 10 enthalten und ist über Windows Update für ältere Betriebssysteme erhältlich und für Windows Vista über Windows 8.1. Eine neu verteilbare Version ist für Windows XP verfügbar. Als Komponente des Betriebssystems werden UCRT-Updates und die UCRT-Wartung von Windows Update unabhängig von Visual Studio und Microsoft C++-Compilerversionen verwaltet. Da die UCRT eine Windows-Komponente ist, empfehlen für zur Sicherheit und Erleichterung von Updates sowie für eine kleinere Imagegröße die zentrale Bereitstellung der UCRT für Ihre App.

Sie können die UCRT unter jeder Version von Windows verwenden, die von Visual Studio 2015 oder Visual Studio 2017 unterstützt wird. Sie können die URCT über ein vcredist-Paket für unterstützte Versionen von Windows neu verteilen, die nicht Windows 10 sind. Die vcredist-Pakete enthalten die UCRT-Komponenten und installieren diese automatisch auf Windows-Betriebssystemen, auf denen sie nicht automatisch installiert sind. Weitere Informationen finden Sie unter [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md).

Eine lokale Bereitstellung der App der UCRT wird zwar unterstützt, wird jedoch aus Leistungs- und Sicherheitsgründen nicht empfohlen. Die DLLs für die lokale Bereitstellung der App sind als Teil des Windows SDK im Unterverzeichnis **redist** enthalten. Die erforderlichen DLLs enthalten „ucrtbase.dll“ und eine Reihe **APISet-Weiterleitungs**-DLLs mit dem Namen „api-ms-win-_subset_.dll“. Die Reihe der erforderlichen DLLs auf jedem Betriebssystem variiert, deshalb empfiehlt es sich, dass Sie alle DLLs einschließen, wenn Sie die lokale Bereitstellung der App verwenden. Zusätzliche Details und Hinweise zu der lokalen App-Bereitstellung finden Sie unter [Deployment in Visual C++ (Bereitstellung in Visual C++)](../ide/deployment-in-visual-cpp.md).

## <a name="changes-to-the-universal-crt-functions-and-macros"></a>Änderungen an den Universal CRT-Funktionen und -Makros

Viele Funktionen wurden in der UCRT hinzugefügt oder aktualisiert, um die ISO C99-Konformität zu verbessern und Probleme mit der Codequalität und Sicherheit zu beheben. In einigen Fällen erfordert dies beeinträchtigende Änderungen an der Bibliothek. Wenn Ihr Code bei der Verwendung einer älteren Version der CRT sauber kompiliert wird, jedoch während der Kompilierung unter Verwendung der CRT beeinträchtigt wird, müssen Sie Ihren Code ändern, damit Sie von diesen Updates und Features profitieren können. Eine ausführliche Liste aller wichtigen Änderungen und Updates für die CRT, die in der Universal CRT ermittelt wurden, finden Sie im Abschnitt [C Runtime Library (CRT) (C-Laufzeitbibliothek (CRT))](visual-cpp-change-history-2003-2015.md#BK_CRT) des Änderungsverlaufs von Visual C++. Sie enthält die betroffenen Header und Funktionen, die Sie zur Identifizierung der Änderungen verwenden können, die in Ihrem Code erforderlich sind.

## <a name="see-also"></a>Siehe auch

[Visual C++-Handbuch: Portieren und Aktualisieren](visual-cpp-porting-and-upgrading-guide.md)<br/>
[Überblick über potenzielle Aktualisierungsprobleme (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Aktualisieren von Projekten von früheren Versionen von Visual C++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Änderungsverlauf von Visual C++ von 2003 bis 2015](visual-cpp-change-history-2003-2015.md)<br/>
[Verbesserungen bei der Übereinstimmung mit C++-Standards in Visual C++ 2017](../cpp-conformance-improvements-2017.md)
