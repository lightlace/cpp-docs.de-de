---
title: Anwendungstyp, MFC-Anwendungs-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df0b938186716ab86b8eaeadd69d123ff14e57e0
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808770"
---
# <a name="application-type-mfc-application-wizard"></a>Anwendungstyp, MFC-Anwendungs-Assistent

Mithilfe dieser Seite des der [MFS-Anwendungsassistenten](../../mfc/reference/mfc-application-wizard.md) zum Entwerfen und zu grundlegende Funktionen zu einer neuen MFC-Anwendung hinzufügen.

- **Anwendungstyp**

   Gibt den Typ von dokumentunterstützung, die Sie in Ihrer Anwendung erstellen möchten. Der Typ der Anwendung, die Sie auswählen, bestimmt die Optionen der Benutzeroberfläche, die für Ihre Anwendung verfügbar sind. Finden Sie unter [Benutzeroberflächen-Features, MFC-Anwendungs-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md) für Weitere Informationen.

   Weitere Informationen zu den Arten von Dokumenten finden Sie unter:

   - [SDI und MDI](../../mfc/sdi-and-mdi.md)

   - [Rahmenfenster](../../mfc/frame-windows.md)

   - [Rahmenfensterklassen](../../mfc/frame-window-classes.md)

   - [Dokumente, Ansichten und das Framework](../../mfc/documents-views-and-the-framework.md)

   - [Dialogfelder](../../mfc/dialog-boxes.md)

   |Option|Beschreibung|
   |------------|-----------------|
   |**Einzelnes Dokument**|Erstellt eine single Document Interface (SDI)-Architektur für Ihre Anwendung eine View-Klasse, in denen basiert auf [CView-Klasse](../../mfc/reference/cview-class.md). Sie können ändern, dass die Basisklasse für die Ansicht in der [generierte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten. Verwenden Sie z. B. zum Erstellen einer formularbasierten Anwendung [CFormView-Klasse](../../mfc/reference/cformview-class.md) für die Ansichtsklasse.<br /><br /> Bei dieser Art der Anwendung kann die Dokumentrahmenfenster lediglich ein einzelnes Dokument enthalten.|
   |**Mehrere Dokumente**|Erstellt eine multiple Document Interface (MDI)-Architektur für Ihre Anwendung eine View-Klasse, in denen basiert auf `CView`. Sie können ändern, dass die Basisklasse für die Ansicht in der **generierte Klassen** Seite des Assistenten. Verwenden Sie z. B. zum Erstellen einer formularbasierten Anwendung `CFormView` für die Ansichtsklasse.<br /><br /> Bei dieser Art der Anwendung kann die Dokumentrahmenfenster mehrere untergeordnete Windows enthalten.|
   |**Dokumente im Registerformat**|Platziert jedes Dokument auf einer separaten Registerkarte an.|
   |**Auf Dialogfeldern basierend**|Erstellt eine auf Dialogfeldern basierende Architektur für Ihre Anwendung, in dem anhand eine Dialogfeldklasse `CDialog`. (Um ein HTML-Dialogfeld zu erstellen, aktivieren Sie das **HTML-Dialogfeld verwenden**.)|
   |**Verwenden Sie HTML-Dialogfeld**|Dialogfeld Feld nur für Anwendungen. Leitet die Dialogfeldklasse von [CDHtmlDialog-Klasse](../../mfc/reference/cdhtmldialog-class.md) anstelle von [CDialog-Klasse](../../mfc/reference/cdialog-class.md). Wenn Sie dieses Kontrollkästchen `CDHtmlDialog` finden Sie der **Basisklasse** im Feld der [generierte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten.<br /><br /> Ein `CDHtmlDialog`-abgeleiteten Dialogfelds HTML-basierte Dialogfelder anzeigt, tauscht Daten mit HTML steuert und HTML-Ereignisse behandelt.|
   |**Mehrere Dokumente mit der höchsten Ebene**|Erstellt eine Architektur, die mehrere der obersten Ebene für Ihre Anwendung eine View-Klasse, in denen basiert auf `CView`.<br /><br /> Bei dieser Art von Anwendung, wenn ein Benutzer klickt **neu** (oder **neuer Frame**) auf die **Datei** im Menü die Anwendung erstellt ein Fenster, dessen übergeordnetes Element implizit den Desktop ist. Der neue Dokumentrahmen wird in der Taskleiste angezeigt und ist nicht beschränkt auf den Clientbereich des Anwendungsfensters.|

- **Unterstützung für die Dokument-/Ansicht**

   Gibt an, ob Ihre Anwendung Dokument-/Ansichtarchitektur einschließt, mit der [CDocument-Klasse](../../mfc/reference/cdocument-class.md) und [CView-Klasse](../../mfc/reference/cview-class.md) (Standard). Deaktivieren Sie dieses Kontrollkästchen, wenn Sie eine MFC-fremde Anwendung portieren, oder wenn Sie die Größe der kompilierten ausführbaren Datei reduzieren möchten. Standardmäßig ergibt sich eine Anwendung ohne Dokument-/Ansichtarchitektur aus [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md), und er schließt nicht die MFC-Unterstützung für das Öffnen eines Dokuments aus einer Datenträgerdatei.

- **Ressourcensprache**

   Legt die Sprache für Ihre Ressourcen fest. Die Liste zeigt die verfügbaren Sprachen auf Ihrem System, wie Sie von Visual Studio installiert. Wenn Sie eine andere Sprache als Ihre Systemsprache auswählen möchten, muss der entsprechende Vorlagenordner für die jeweilige Sprache bereits installiert sein.

   Die Sprache, die Sie auswählen, wirkt sich die **lokalisierte Zeichenfolgen** Möglichkeit, die [Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Seite des Assistenten.

- **Verwenden von Unicode-Bibliotheken**

   Gibt an, ob die Unicode oder nicht-Unicode-Version von MFC-Bibliotheken verwendet wird.

- **Projektstil**

   Gibt an, ob Ihre Anwendung ein standard MFC, Datei-Explorer, Visual Studio oder Office-Architektur und anzeigen. Weitere Informationen finden Sie unter [erstellen die MFC-Anwendung ein Datei-Explorer-Style](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).

   |Option|Beschreibung|
   |------------|-----------------|
   |**MFC-standard**|Bietet eine MFC-Anwendungsarchitektur standard.|
   |**Datei-Explorer**|Implementiert eine Datei-Explorer-ähnliche Anwendung mithilfe eines unterteilten Fensters, in dem der linke Bereich ist, eine [CTreeView-Klasse](../../mfc/reference/ctreeview-class.md) und der rechte Bereich ist eine [CListView-Klasse](../../mfc/reference/clistview-class.md).|
   |**Visual Studio**|Implementiert eine Visual Studio-ähnliche-Anwendung, die vier andockbare Bereiche enthält (**Dateiansicht**, **Klassenansicht**, **Eigenschaften**, und **Ausgabe**), die davon abgeleitet sind [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) und einem Hauptrahmenfenster, das von abgeleitet ist [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md) (Standard).|
   |**Office**|Implementiert eine Office-ähnliche Anwendung, die ein Menüband enthält, das von abgeleitet ist [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md), eine Outlook-Leiste, das von abgeleitet ist [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md), Titelleiste, die abgeleitet wird [CMFCCaptionBar-Klasse](../../mfc/reference/cmfccaptionbar-class.md), und einen Hauptframe, das von abgeleitet ist [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md).|

- **Visueller Stil und Farben**

   Bestimmt den visuellen Stil der Anwendung an. Die folgenden Optionen sind verfügbar:

   - **Windows Native/Standard**

   - **Office 2003**

   - **Visual Studio 2005**

   - **Office 2007 (blaues Design)**

   - **Office 2007 (Schwarz Design)**

   - **Office 2007 (Silber Design)**

   - **Office 2007 (Aqua Design)**

- **Aktivieren Sie visuelles stilswitching**

   Gibt an, ob der Benutzer den visuellen Stil der Anwendung zur Laufzeit in der Regel ändern kann durch Auswählen des entsprechenden visuellen Stils aus einem Menü oder das Menüband.

- **Verwendung von MFC**

   Gibt an, wie mit der MFC-Bibliothek zu verknüpfen. Standardmäßig wird MFC als einer gemeinsam genutzten DLL verknüpft.

   |Option|Beschreibung|
   |------------|-----------------|
   |**MFC in einer gemeinsam genutzten DLL verwenden**|Die MFC-Bibliothek verknüpft mit einer Anwendung als eine freigegebene DLL. Die Anwendung aufruft, die MFC-Bibliothek zur Laufzeit. Diese Option verringert die Datenträger- und speicheranforderungen von Anwendungen, die mehrere ausführbare Dateien bestehen, die die MFC-Bibliothek verwenden. Win32- und MFC-Anwendungen können Funktionen in der DLL (Standard) aufrufen.|
   |**Verwenden Sie MFC in einer statischen Bibliothek.**|Verknüpft eine Anwendung zum Zeitpunkt der Erstellung der statischen MFC-Bibliothek.|

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)<br/>
[Für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md)

