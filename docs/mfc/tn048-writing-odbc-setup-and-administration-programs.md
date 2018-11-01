---
title: 'TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen für MFC-Datenbankanwendungen'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.odbc
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
ms.openlocfilehash: b31ceb8bfc48decb5387d386ee8e8b64822f72ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584126"
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>TN048: Schreiben von ODBC-Einrichtungs- und Verwaltungsprogrammen für MFC-Datenbankanwendungen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Anwendungen mithilfe von MFC-Datenbankklassen benötigen ein Setup-Programm, das ODBC-Komponenten installiert. Möglicherweise benötigen sie auch über eine ODBC-Verwaltung-Programm, mit denen Informationen zu den verfügbaren Treiber, um Standardtreiber anzugeben und so konfigurieren Sie Datenquellen abgerufen werden. Dieser Hinweis beschreibt die Verwendung der ODBC-Installer-API diese Programme zu schreiben.

##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> Schreiben Sie eine ODBC-Setup-Programm

Eine MFC-datenbankanwendung erfordert der ODBC-Treiber-Manager (ODBC. DLL) und ODBC-Treiber, um auf Datenquellen erhalten zu können. Viele ODBC-Treiber erfordern ebenfalls zusätzlichen Netzwerkfehlern und Kommunikationsfehlern DLLs. Die meisten ODBC-Treiber, die mit einem Setup-Programm, das installieren die erforderlichen Komponenten für die ODBC-ausgeliefert werden. Verwenden von MFC-Datenbankklassen Anwendungsentwickler können Aktionen ausführen:

- Basieren Sie auf die treiberspezifischen Setupprogramme, zum Installieren von ODBC-Komponenten. Dies erfordert, dass keine weitere Arbeit an der Entwickler Teil – Sie können nur vom Treiber Setupprogramm verteilen.

- Alternativ können Sie eigene Setup-Programm schreiben, das der Treiber-Manager und der Treiber installiert.

Die ODBC-Installer-API kann verwendet werden, anwendungsspezifische-Setup-Programme zu schreiben. Die Funktionen in den API-Installer werden von der ODBC-Installationsprogramm-DLL implementiert – ODBCINST. Die DLL auf 16-Bit-Windows und ODBCCP32. Die DLL auf Win32. Kann eine Anwendung aufrufen `SQLInstallODBC` im Installationsprogramm-DLL, die Installieren des ODBC-Treiber-Managers, ODBC-Treiber und andere Übersetzer erforderlich. Anschließend zeichnet er und den installierten Treiber und Übersetzern in die ODBCINST. INI-Datei (oder der Registrierung unter NT). `SQLInstallODBC` erfordert den vollständigen Pfad zu der ODBC. INF-Datei, die enthält die Liste der Treiber installiert werden, und beschreibt die Dateien, die jeden Treiber enthalten. Es enthält auch ähnliche Informationen zu Treibermanager und den Übersetzer. ODBC. INF-Dateien werden in der Regel von Treiberentwickler bereitgestellt.

Ein Programm kann auch einzelne ODBC-Komponenten installieren. Zum Installieren des Treiber-Managers ein Programm zunächst ruft `SQLInstallDriverManager` im Installationsprogramm-DLL für das Zielverzeichnis für den Treiber-Manager zu erhalten. Dies ist normalerweise das Verzeichnis, in dem Windows-DLLs befinden. Das Programm verwendet dann die Informationen im Abschnitt [ODBC-Treiber-Manager] der ODBC. INF-Datei, um die Treiber-Manager und zugehörige Dateien aus der Installations-CD in dieses Verzeichnis zu kopieren. Um von einem einzelnen Treiber zu installieren, ein Programm zunächst ruft `SQLInstallDriver` im Installationsprogramm-DLL für die ODBCINST die Treiber-Spezifikation hinzugefügt. INI-Datei (oder der Registrierung unter NT). `SQLInstallDriver` Gibt das Zielverzeichnis des Treibers zurück, in der Regel auf das Verzeichnis, in der Windows-DLLs befinden. Das Programm verwendet dann die Informationen in den ODBC-Abschnitt des Treibers. INF-Datei, die der Treiber-DLL und die zugehörigen Dateien von der Installations-CD in dieses Verzeichnis zu kopieren.

Weitere Informationen zu ODBC. INF, ODBCINST. INI-Datei und mit dem Installer-API finden Sie unter ODBC SDK *Programmer's Reference* Kapitel 19, ODBC-Software installieren.

##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> Schreiben von ODBC-Administrator

Eine MFC-datenbankanwendung kann einrichten und Konfigurieren von ODBC-Datenquellen in einem der zwei Möglichkeiten, wie folgt:

- Verwenden Sie den ODBC-Administrator (verfügbar als ein Programm oder als Elemente der Systemsteuerung).

- Erstellen Sie Ihr eigenes Programm so konfigurieren Sie Datenquellen.

Ein Programm, das Datenquellen konfiguriert ist, Funktionsaufrufe, um die Installationsprogramm-DLL. Das Installationsprogramm-DLL Ruft ein Setup-DLL für eine Datenquelle konfigurieren. Es gibt ein Setup-DLL für jeden Treiber. Es kann der Treiber-DLL selbst, oder auf einer separaten DLL sein. Der Setup-DLL für fragt Informationen, die der Treiber benötigt, für die Verbindung der Datenquelle und das Standard-Konvertierungsprogramm unterstützt. Es ruft dann den Installer, DLL und Windows-APIs, um diese Informationen in die ODBC zu erfassen. INI-Datei (oder Registrierung).

Um ein Dialogfeld angezeigt, mit denen ein Benutzer kann hinzufügen, ändern und Löschen von Datenquellen, ein Programm ruft `SQLManageDataSources` im DLL-Installer. Diese Funktion wird aufgerufen, wenn das Installationsprogramm die DLL in der Systemsteuerung aufgerufen wird. Zum Hinzufügen, ändern oder Löschen einer Datenquelle `SQLManageDataSources` Aufrufe `ConfigDSN` in der Setup-DLL für den Treiber, die diese Datenquelle zugeordnet. Datenquellen, die direkt hinzufügen, ändern oder Löschen von Daten, ein Programm ruft `SQLConfigDataSource` im DLL-Installer. Die Anwendung übergibt den Namen der Datenquelle und eine Option aus, die die auszuführende Aktion angibt. `SQLConfigDataSource` Aufrufe `ConfigDSN` in der Setup-DLL und übergibt sie die Argumente vom `SQLConfigDataSource`.

Weitere Informationen finden Sie in der ODBC-SDK *Programmer's Reference* Kapitel 23, Setup-DLL-Funktionsreferenz und Kapitel 24, Installer DLL Function Reference.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

