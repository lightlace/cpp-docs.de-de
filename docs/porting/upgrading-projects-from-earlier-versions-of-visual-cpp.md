---
title: Aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio
description: Hier erfahren Sie, wie ein Upgrade auf Microsoft Visual C++-Projekte aus älteren Visual Studio-Versionen ausgeführt wird.
ms.date: 10/29/2019
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
ms.openlocfilehash: b317271a9cd0873e60a6dd9acd1b73a766aaea19
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627167"
---
# <a name="upgrade-c-projects-from-earlier-versions-of-visual-studio"></a>Aktualisieren C++ von Projekten aus früheren Versionen von Visual Studio

Zum Aktualisieren eines Projekts, das in Visual Studio 2008 oder einer früheren Version erstellt wurde, müssen Sie zunächst Visual Studio 2010 verwenden, um das Projekt vom VCBuild-Format (. vcproj) in das MSBuild-Format (. vcxproj) zu konvertieren. Weitere Informationen finden Sie unter [Anweisungen für Visual Studio 2008](use-native-multi-targeting.md#instructions-for-visual-studio-2008).

Um ein Projekt zu aktualisieren, das in Visual Studio 2010 oder höher erstellt wurde, öffnen Sie einfach das Projekt in der aktuellen Version von Visual Studio. Visual Studio bietet die Option, um das Projekt auf das aktuelle Schema zu aktualisieren. Wenn Sie **Nein**auswählen und die ältere Version von Visual Studio auf Ihrem Computer vorhanden ist, können Sie im Projekt in einer neueren Version von Visual Studio arbeiten und weiterhin das ältere Toolset als Ziel festlegen. Wenn Ihr Projekt beispielsweise weiterhin unter Windows XP ausgeführt werden muss, können Sie es auf Visual Studio 2019 aktualisieren, aber Sie müssen das Toolset als v141 oder früher angeben. Weitere Informationen finden Sie unter [Use native multi-targeting in Visual Studio to build old projects (Verwenden der nativen Festlegung von Zielversionen in Visual Studio, um alte Projekte zu erstellen)](use-native-multi-targeting.md). Wenn Sie **Ja**auswählen, wird das Projekt konvertiert und kann nicht wieder in die frühere Version konvertiert werden. Daher empfiehlt es sich, in Upgradeszenarien eine Kopie der vorhandenen Projekt-und Projektmappendateien zu erstellen.

## <a name="upgrade-reports"></a>Aktualisieren von Berichten

Wenn Sie ein Projekt aktualisieren, erhalten Sie einen Upgradebericht, der auch als „UpgradeLog.htm“ in Ihrem Projektordner gespeichert wird. Der Upgradebericht enthält eine Zusammenfassung der gefundenen Probleme und einige Informationen zu Änderungen, die vorgenommen wurden, einschließlich:

1. Projekteigenschaften

2. Includedateien

3. Code, der aufgrund von Verbesserungen der Compilerkonformität oder Änderungen am Standard nicht mehr ordnungsgemäß kompiliert wird

4. Code, der sich auf Visual Studio- oder Windows-Funktionen stützt, die nicht mehr verfügbar sind, oder Headerdateien, die entweder in einer Standardinstallation von Visual Studio nicht enthalten sind oder aus dem Produkt entfernt wurden

5. Code, der aufgrund von Änderungen an APIs nicht mehr kompiliert wird, wie z. B. umbenannte APIs, geänderte Funktionssignaturen oder veraltete Funktionen

6. Code, der aufgrund von Änderungen bei der Diagnose nicht mehr kompiliert wird, wie z. b. eine Warnung, die zu einem Fehler wird

7. Linkerfehler aufgrund von geänderten Bibliotheken, insbesondere bei Verwendung von /NODEFAULTLIB

8. Laufzeitfehler oder unerwartete Ergebnisse aufgrund von Verhaltensänderungen

9. Fehler, die in den Tools eingeführt wurden. Wenn ein Problem auftritt, melden Sie dies dem Microsoft Visual C++-Team über die normalen Supportkanäle oder die [Visual Studio-Website für die C++-Entwicklercommunity](https://developercommunity.visualstudio.com/spaces/62/index.html).

Einige aktualisierte Projekte und Projektmappen können ohne Änderung erfolgreich erstellt werden. Die meisten Projekte erfordern jedoch wahrscheinlich Änderungen an den Projekteinstellungen und dem Quellcode. Es gibt keine einzige korrekte Methode, um diese zu beheben, aber es wird empfohlen, eine Art von phasenweise durchzugehen. Bevor Sie beginnen, lesen Sie den [Überblick über mögliche Upgradeprobleme](../porting/overview-of-potential-upgrade-issues-visual-cpp.md) , um weitere Informationen zu vielen häufigen Fehlern zu erhalten.

 1. Legen Sie das Platt Form Toolset, C++ den sprach Standard und Windows SDK Version (falls zutreffend) auf die gewünschten Versionen fest. (**Projekt** > **Eigenschaften** > **Konfigurations Eigenschaften** > **Allgemein**)
 1. Wenn viele Fehler auftreten, deaktivieren Sie die Option " [permissive-](../build/reference/permissive-standards-conformance.md) Option" (**Projekt** > **Eigenschaften** > **Konfigurations Eigenschaften** > **C/C++**  > **Sprache**) und die [Code Analyse. ](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)(**Projekt** > **Eigenschaften** > **Konfigurations Eigenschaften** > **Code Analyse**) vorübergehend, um die Fehler Anzahl zu verringern.
 1. Stellen Sie sicher, dass alle Abhängigkeiten vorhanden sind und dass die Includepfade oder Bibliotheks Speicherorte korrekt sind. (**Projekt** > **Eigenschaften** > **Konfigurations Eigenschaften** > **VC + +-Verzeichnisse**)
 1. Identifizieren und beheben Sie Fehler aufgrund von Verweisen auf APIs, die nicht mehr vorhanden sind.
 1. Beheben Sie alle restlichen Fehler, die die Kompilierung verhindern. Weitere Informationen finden Sie unter [Übersicht über mögliche Upgradeprobleme](../porting/overview-of-potential-upgrade-issues-visual-cpp.md) für Fehlerbehebungen für häufige Fehler.
 1. Aktivieren Sie den Wert für **"deaktivieren"** , und beheben Sie alle neuen Fehler, die aufgrund von nicht konformen Code auftreten, der zuvor in MSVC kompiliert wurde.
 1. Aktivieren Sie die Code Analyse, um potenzielle Probleme oder veraltete Codierungs Muster zu identifizieren, die nicht mehr als akzeptabel erachtet werden. Wenn bei der Code Analyse viele Fehler ausgegeben werden, können Sie einige der Warnungen deaktivieren, damit Sie sich zunächst auf die wichtigsten Warnungen konzentrieren können. Die IDE kann für einige Arten von Problemen bei schnellen Korrekturen helfen.
 1. Nehmen Sie andere Möglichkeiten zur Modernisierung des Codes in Erwägung, indem Sie beispielsweise benutzerdefinierte Datenstrukturen und Algorithmen durch C++ die der Standardbibliothek oder die Boost Open Source-Bibliothek ersetzen. Durch die Verwendung von Standard Features vereinfachen Sie es anderen Benutzern, den Code zu verwalten, und Sie können auch sicher sein, dass der Code von vielen Experten des Standards Committee und der umfassenderen C++ Community gut getestet und überprüft wurde.

Um Fehlerbehebung zu beheben, versuchen Sie, eine Frage zu Stack Overflow oder [ C++ Entwickler-Community](https://developercommunity.visualstudio.com/spaces/62/index.html)zu suchen oder zu veröffentlichen.

## <a name="in-this-section"></a>In diesem Abschnitt

[Überblick über potenzielle Upgradeprobleme (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)<br/>
[Aktualisieren Ihres Codes auf die Universal CRT](upgrade-your-code-to-the-universal-crt.md)<br/>
[Aktualisieren von WINVER und _WIN32_WINNT](modifying-winver-and-win32-winnt.md)<br/>
[Fix your dependencies on library internals (Beheben Ihrer Abhängigkeiten auf bibliotheksinternen Elementen)](fix-your-dependencies-on-library-internals.md)<br/>
[Gleitkomma-Migrationsprobleme](floating-point-migration-issues.md)<br/>
[C++in Visual Studio 2019 veraltete Features](features-deprecated-in-visual-studio.md)<br/>
[VCBuild im Vergleich zu MSBuild](build-system-changes.md)<br/>
[Port-Drittanbieterbibliotheken](porting-third-party-libraries.md)<br/>

## <a name="see-also"></a>Siehe auch

[Neues bei Visual C++ in Visual Studio 2015](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)<br/>
[Port Daten Anwendungen](../data/data-access-programming-mfc-atl.md)<br/>
