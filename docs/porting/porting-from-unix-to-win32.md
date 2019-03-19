---
title: Portieren von UNIX auf Win32
ms.date: 08/02/2018
helpviewer_keywords:
- APIs [C++], porting to Win32
- Windows API [C++], migrating from UNIX
- migration [C++]
- UNIX [C++], porting to Win32
- porting to Win32 [C++], from UNIX
- porting to Win32 [C++]
- Win32 applications [C++], migrating from UNIX
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
ms.openlocfilehash: 325cdb86f61f658776c69057022c005c389492d3
ms.sourcegitcommit: 9e85c2e029d06b4c1c69837437468718b4d54908
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "57813902"
---
# <a name="porting-from-unix-to-win32"></a>Portieren von UNIX auf Win32

Bei der Anwendungsmigration von UNIX auf Windows stehen eine Reihe von Optionen zur Verfügung:

- Verwenden von UNIX-Bibliotheken, um Anwendungen von UNIX auf Win32 zu portieren

- Direktes Portieren von UNIX-Anwendungen auf Win32

- Ausführen von UNIX-Anwendungen unter Windows mit dem POSIX-Subsystem

## <a name="unix-libraries"></a>UNIX-Bibliotheken

Eine Option, die UNIX-Programmierer in der Regel in Betracht ziehen, ist das Verwenden von UNIX-Bibliotheken von Drittanbietern, um ihren UNIX-Code als Win32-Anwendung zu kompilieren. Mehrere kommerzielle Bibliotheken (sowie mindestens eine Public Domain-Bibliothek) erfüllen diesen Zweck. Dieses Verfahren kann für einige Anwendungen sinnvoll sein. Der Vorteil dieser Portierungsbibliotheken besteht darin, dass sie den Anfangsaufwand für die Portierung minimieren. Der Hauptnachteil liegt insbesondere für konkurrierende Softwareprodukte darin, dass eine direkte Win32-Portierung einer Anwendung in der Regel schneller ist und zwangsläufig eine größere Funktionalität besitzt. Es kann sich für eine Anwendung als hinderlich erweisen, zur Durchführung von Win32-Aufrufen ihre UNIX-Shell zu verlassen, um unter Windows leistungsfähiger zu sein.

In der folgenden Liste sind Ressourcen von Microsoft und von Drittanbietern aufgeführt, die dem Portieren und der Unterstützung der UNIX-Migration auf Visual C++ dienen:

### <a name="unix-migration-guides"></a>UNIX-Migrationshandbücher

Technische Hilfe zur Codemigration von UNIX zur Win32-Umgebung finden Sie im [UNIX Custom Application Migration Guide](https://technet.microsoft.com/library/bb656290.aspx).

Der [Unix Migration Project Guide](https://technet.microsoft.com/library/bb656287.aspx) ergänzt den UNIX Custom Application Migration Guide mit weiterführender Hilfe zur Migration grundlegender Projekte von UNIX zu Win32. Das Handbuch stellt einen Ratgeber zu Themen in jeder Phase der Projektmigration dar.

### <a name="microsoft-windows-services-for-unix-sfu"></a>Microsoft Windows Services for UNIX (SFU)

Microsoft Windows Services for UNIX (SFU) stellen eine vollständige Auswahl von plattformübergreifenden Diensten für die Integration von Windows in vorhandene UNIX-Umgebungen dar. Services for UNIX bietet Dateifreigaben, remoten Zugriff und Administration, Kennwortsynchronisierung, allgemeine Verzeichnisverwaltung, eine Auswahl gebräuchlicher Dienstprogramme und eine Shell.

[Windows Services für UNIX](http://www.microsoft.com/downloads/details.aspx?FamilyID=896c9688-601b-44f1-81a4-02878ff11778&displaylang=en)

### <a name="interopsystemscom"></a>InteropSystems.com

[http://www.interopsystems.com/](http://www.interopsystems.com/)

Dies ist die Website eines Drittanbieters für Software, die das Portieren von UNIX auf Win32 unterstützt.

### <a name="c-boost-web-site"></a>Website C++ Boost

[http://boost.sourceforge.net/regression-logs/](http://boost.sourceforge.net/regression-logs/)

[http://boost.sourceforge.net/boost-build2/](http://boost.sourceforge.net/boost-build2/)

## <a name="porting-unix-applications-directly-to-win32"></a>Direktes Portieren von UNIX-Anwendungen auf Win32

Eine weitere Möglichkeit besteht in dem direkten Portieren von UNIX-Anwendungen auf Win32. Durch die Verwendung von ANSI C/C++-Bibliotheken und kommerziellen C-Compilerbibliotheken sind die herkömmlichen Systemaufrufe, die von UNIX-Anwendungen verwendet werden, größtenteils auch in Win32-Anwendungen verfügbar.

Das Ausgabemodell der **stdio**-basierten Anwendungen muss nicht geändert werden, da die Win32-Konsolen-APIs das **stdio**-Modell imitieren und Versionen von *curses* vorhanden sind, die Win32-Konsolen-APIs verwenden. Weitere Informationen finden Sie unter [SetConsoleCursorPosition](/windows/console/setconsolecursorposition).

Auf Berkeley-Sockets basierende Anwendungen müssen nur geringfügig geändert werden, um als Win32-Anwendungen ausgeführt werden zu können. Beim Entwerfen der Windows Sockets-Schnittstelle wurde auf Portabilität mit BSD-Sockets geachtet, wobei nur minimale Änderungen, die in der Einführung der WinSock-Spezifikation beschrieben werden, in Kauf genommen werden müssen.

Windows unterstützt den DCE-kompatiblen RPC, sodass RPC-Anwendungen problemlos verwendet werden können. Weitere Informationen finden Sie unter [RPC Functions (RPC-Funktionen)](/windows/desktop/Rpc/rpc-functions).

Einer der Bereiche mit den deutlichsten Unterschieden ist das Prozessmodell. UNIX verfügt über `fork`, Win32 nicht. Abhängig davon, wie `fork` und die Codebasis verwendet werden, können in Win32 zwei APIs verwendet werden: `CreateProcess` und `CreateThread`. Eine UNIX-Anwendung, die mehrere Kopien von sich selbst erstellt, kann in Win32 so überarbeitet werden, dass sie entweder mehrere Prozesse oder einen Prozess mit mehreren Threads besitzt. Bei Verwendung mehrerer Prozesse stehen mehrere IPC-Methoden für die Kommunikation zwischen Prozessen zur Verfügung (und eventuell auch für die Aktualisierung von Code und Daten des neuen Prozesses in Anpassung an den übergeordneten Prozess, falls die von `fork` bereitgestellte Funktionalität benötigt wird). Weitere Informationen zu IPC finden Sie unter [Interprocess Communications (Prozessübergreifende Kommunikation)](/windows/desktop/ipc/interprocess-communications).

Die Grafikmodelle von Windows und UNIX weisen große Unterschiede auf. UNIX verwendet die X Window System GUI, während Windows GDI verwendet. Obwohl beide Schnittstellen ähnlich konzipiert sind, ist keine einfache Zuordnung zwischen X-APIs und GDI-APIs möglich. Jedoch ist OpenGL-Unterstützung für die Migration von OpenGL-basierten UNIX-Anwendungen verfügbar. Außerdem stehen X-Clients und X-Server für Windows zur Verfügung. Informationen über GDI finden Sie unter [Gerätekontexte](/windows/desktop/gdi/device-contexts).

UNIX-Basisanwendungen, darunter zahlreiche CGI-Anwendungen, sollten in der Regel leicht auf Visual C++, das unter Windows ausgeführt wird, portierbar sein. Funktionen wie `open`, `fopen`, `read`, `write` und andere sind in der Visual C++-Laufzeitbibliothek verfügbar. Darüber hinaus werden C-UNIX-APIs und Win32-APIs in einem Verhältnis von 1:1 zugeordnet: `open` zu `CreateFile`, `read` zu `ReadFile`, `write` zu `WriteFile`, `ioctl` zu `DeviceIOControl`, `close` zu `CloseFile` usw.

## <a name="windows-posix-subsystem"></a>POSIX-Subsystem unter Windows

Eine weitere Option für UNIX-Programmierer stellt das POSIX-Subsystem unter Windows dar. Dies unterstützt jedoch nur POSIX 1003.1, die einzige standardisierte POSIX-Version, als Windows NT entwickelt wurde. Seitdem bestand wenig Nachfrage nach Erweiterungen dieses Subsystems, da die meisten Anwendungen in Win32 konvertiert wurden. Das 1003.1-System ist für Anwendungen mit einem vollständigen Funktionsumfang wenig interessant, da viele Funktionen darin fehlen (z. B. die Funktionen von 1003.2 wie Netzwerkunterstützung usw.). Anwendungen mit vollem Featureumfang, die unter dem POSIX-Subsystem von Windows ausgeführt werden, haben keinen Zugriff auf die in Win32-Anwendungen verfügbaren Windows-Funktionen wie Speicherabbilddateien oder Netzwerk- und Grafikfunktionen. Anwendungen wie VI, LS und GREP sind das Hauptanwendungsgebiet für das POSIX-Subsystem unter Windows.

## <a name="see-also"></a>Siehe auch

[Visual C++-Handbuch: Portieren und Aktualisieren](visual-cpp-change-history-2003-2015.md)<br/>
[UNIX](../c-runtime-library/unix.md)<br/>
[Rückschlussregeln](../build/reference/inference-rules.md)
