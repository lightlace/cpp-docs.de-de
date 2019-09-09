---
title: Erweiterte Features, MFC-Anwendungs-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.advanced
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
ms.openlocfilehash: dc2b745bf97dff65a3612c29745c9d0e455a347d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507809"
---
# <a name="advanced-features-mfc-application-wizard"></a>Erweiterte Features, MFC-Anwendungs-Assistent

Unter diesem Thema werden die Optionen für zusätzliche Funktionen für Ihre Anwendung aufgeführt, zum Beispiel eine Hilfefunktion, Druckunterstützung usw. Legen Sie in den einzelnen Abschnitten zusätzliche Unterstützungsoptionen für die erweiterten Funktionen fest.

- **Kontextbezogene Hilfe (HTML)**

   Generiert eine Gruppe von Hilfedateien für die kontextbezogene Hilfe, die über F1 und ein Hilfemenü verfügbar ist, oder durch Klicken auf die Schaltfläche **Hilfe** in einem Dialogfeld. Zur Unterstützung der Hilfe ist der Hilfecompiler erforderlich. Sie können den Hilfecompiler nachträglich installieren, indem Sie Setup erneut ausführen.

   Siehe [HTML-Hilfe: Weitere Informationen finden Sie unter kontextbezogene](../../mfc/html-help-context-sensitive-help-for-your-programs.md) Hilfe für Ihre Programme und [Hilfedateien (HTML-Hilfe)](../../build/reference/help-files-html-help.md) .

- **Druck-und Druckvorschau**

   Generiert den Code zum Behandeln der Druck-, drucksetup-und Druckvor Schau Befehle durch Aufrufen von Element Funktionen in der [CView-Klasse](../../mfc/reference/cview-class.md) aus der MFC-Bibliothek. Zusätzlich fügt der Assistent dem Anwendungsmenü Befehle für diese Funktionen hinzu. Die Druckunterstützung ist nur für Anwendungen verfügbar, die **Unterstützung für Dokument-/Ansichtarchitektur** auf der Seite [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md) des Assistenten angeben. Dokument-/Ansichtsanwendungen verfügen standardmäßig über Druckunterstützung.

- **Automatisierung**

   Gibt an, dass in der Anwendung Objekte bearbeitet werden können, die in einer anderen Anwendung implementiert wurden, bzw. stellt der Anwendung Automatisierungsclients zur Verfügung.

- **ActiveX-Steuerelemente**

   Unterstützt ActiveX-Steuerelemente (Standard). Wenn Sie diese Option nicht auswählen und später ActiveX-Steuerelemente in das Projekt einfügen möchten, müssen Sie in der [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) -Member-Funktion der Anwendung einen aufzurufenden [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) -Befehl hinzufügen.

- **MAPI (Messaging-API)**

   Gibt an, dass der Benutzer in der Anwendung E-Mail-Nachrichten erstellen, bearbeiten, übertragen und speichern kann.

- **Windows-Sockets**

   Unterstützt Windows-Sockets, mit denen Sie Anwendungen schreiben können, die über TCP/IP-Netzwerke kommunizieren.

- **Active Accessibility**

   Bietet Unterstützung [für die](/windows/win32/api/oleacc/nn-oleacc-iaccessible) durch [CWnd](../../mfc/reference/cwnd-class.md)abgeleiteten Klassen, die Sie verwenden können, um die Benutzeroberfläche für eine bessere Interaktion mit Barrierefreiheits Clients anzupassen.

- **Gemeinsames Steuerelement Manifest**

   Standardmäßig aktiviert. Erstellt ein Anwendungsmanifest zur Aktivierung der im Lieferumfang von Microsoft Windows XP und von neueren Betriebssystemen enthaltenen DLL für allgemeine Steuerelemente.

   Version 6 der DLL für allgemeine Steuerelemente aktualisiert die Vorläuferversion eines allgemeinen Steuerelements, das von einer vorhandenen Anwendung verwendet wird, nicht automatisch. Um die DLL für allgemeine Steuerelemente, Version 6, verwenden zu können, müssen Sie ein Anwendungsmanifest erstellen, das Ihre Anwendung anweist, die neue DLL zu laden. Die DLL für allgemeine Steuerelemente unterstützt auch Windows XP-Designs.

   Durch ein Anwendungsmanifest können auch andere, von Ihrer Anwendung benötigte DLLs und Versionen festgelegt werden. Weitere Informationen zu Anwendungs Manifesten finden Sie unter [isolierte Anwendungen und](/windows/win32/SbsCs/isolated-applications-and-side-by-side-assemblies-portal) parallele Assemblys in der Windows SDK.

- **Neustart-Manager unterstützen**

   Fügt Unterstützung für den [Windows-Neustart-Manager](/windows/win32/RstMgr/using-restart-manager)hinzu. In diesem Video wird gezeigt, wie der Neustart-Manager von MFC verwendet wird: [Gewusst wie: Verwenden Sie den neuen Neustart](/previous-versions/visualstudio/visual-studio-2010/dd831853(v%3dvs.100))-Manager.

- **Erweiterte Frame Bereiche**

   |Option|Beschreibung|
   |------------|-----------------|
   |**Explorer-Docking Bereich**|Erstellt einen andockbaren Bereich, der dem Visual Studio- **Projektmappen-Explorer** Links vom Hauptrahmen Fenster ähnelt.|
   |**Andockbarer Ausgabe Rahmen**|Erstellt einen andockbaren Bereich, der dem Visual Studio- **Ausgabe** Bereich ähnelt, der sich unter dem Hauptrahmen Fenster befindet.|
   |**Andockbarer Eigenschaften Bereich**|Erstellt einen andockbaren Bereich, der dem Visual Studio- **Eigenschaften** Bereich rechts vom Hauptrahmen Fenster ähnelt.|
   |**Navigationsbereich**|Erstellt einen andockbaren Bereich, der der Outlook-Navigationsleiste links vom Hauptrahmenfenster ähnelt.|
   |**Titelleiste**|Erstellt eine Titelleiste im Office-Stil über dem Hauptrahmenfenster.|

- **Anzahl der Dateien in der Liste der zuletzt geöffneten Dateien**

   Gibt die Anzahl der Dateien an, die in der Liste der zuletzt verwendeten Dateien angezeigt werden soll. Die Anzahl beträgt standardmäßig 4.

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)
