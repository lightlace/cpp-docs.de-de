---
title: "Anwendungstyp, MFC-Anwendungs-Assistent"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.apptype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Statische Bibliotheken, MFC"
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungstyp, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md) können Sie grundlegende Features entwerfen und diese einer neuen MFC\-Anwendung hinzufügen.  
  
 **Anwendungstyp**  
 Gibt den Typ der Dokumentunterstützung an, die in die Anwendung implementiert werden soll.  Durch den ausgewählten Anwendungstyp werden die Optionen der Benutzeroberfläche bestimmt, die für die Anwendung verfügbar sind.  Weitere Informationen finden Sie unter [Benutzeroberflächen\-Features, MFC\-Anwendungs\-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md).  
  
 Weitere Informationen über diese Dokumenttypen finden Sie unter:  
  
-   [SDI und MDI](../../mfc/sdi-and-mdi.md)  
  
-   [Rahmenfenster](../../mfc/frame-windows.md)  
  
-   [Rahmenfensterklassen](../../mfc/frame-window-classes.md)  
  
-   [Dokumente, Ansichten und das Framework](../../mfc/documents-views-and-the-framework.md)  
  
-   [Dialogfelder](../../mfc/dialog-boxes.md)  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Einfaches Dokument**|Erstellt eine SDI \(Single Document Interface\)\-Architektur mit einer auf [CView Class](../../mfc/reference/cview-class.md) basierten Ansichtsklasse für die Anwendung.  Die Basisklasse für die Ansicht kann auf der Seite [Erstellte Klassen, MFC\-Anwendungs\-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) des Assistenten geändert werden.  Um beispielsweise eine formularbasierte Anwendung zu erstellen, können Sie [CFormView Class](../../mfc/reference/cformview-class.md) für die Ansichtsklasse verwenden.<br /><br /> Bei diesem Anwendungstyp kann das Rahmenfenster des Dokuments jeweils nur ein Dokument beinhalten.|  
|**Mehrfache Dokumente**|Erstellt eine MDI \(Multiple Document Interface\)\-Architektur mit einer auf `CView` basierten Ansichtsklasse für die Anwendung.  Die Basisklasse für die Ansicht kann auf der Seite **Generierte Klassen** des Assistenten geändert werden.  Um beispielsweise eine formularbasierte Anwendung zu erstellen, können Sie `CFormView` für die Ansichtsklasse verwenden.<br /><br /> Bei diesem Anwendungstyp kann das Rahmenfenster des Dokuments mehrere untergeordnete Fenster enthalten.|  
|**Dokumente im Registerkartenformat**|Platziert jedes Dokument auf einer separaten Registerkarte.|  
|**Auf Dialogfeldern basierend**|Erstellt eine auf Dialogfeldern basierende Architektur mit einer auf `CDialog` basierenden Dialogfeldklasse für die Anwendung. \(Um ein HTML\-Dialogfeld zu erstellen, aktivieren Sie das Kontrollkästchen **HTML\-Dialogfeld verwenden**.\)|  
|**HTML\-Dialogfeld verwenden**|Nur für Anwendungen mit Dialogfeldern.  Leitet die Dialogfeldklasse von [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md) anstatt von [CDialog Class](../../mfc/reference/cdialog-class.md) ab.  Wenn Sie dieses Kontrollkästchen aktivieren, wird `CDHtmlDialog` im Feld **Basisklasse** auf der Seite [Erstellte Klassen, MFC\-Anwendungs\-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) des Assistenten aufgeführt.<br /><br /> Ein von `CDHtmlDialog` abgeleitetes Dialogfeld zeigt HTML\-basierte Dialogfelder an, führt den Datenaustausch mithilfe von HTML\-Steuerelementen aus und verwaltet HTML\-Ereignisse.|  
|**Mehrere Dokumente der höchsten Ebene**|Erstellt eine Architektur, die mehrere Dokumente der höchsten Ebene unterstützt, mit einer auf `CView` basierten Ansichtsklasse für die Anwendung.<br /><br /> Wenn ein Benutzer bei diesem Anwendungstyp im Menü **Datei** auf **Neu** \(oder auf **Neuer Rahmen**\) klickt, erstellt die Anwendung ein Fenster, dessen implizites übergeordnetes Element der Desktop ist.  Der neue Dokumentrahmen wird in der Taskleiste angezeigt und ist nicht auf den Clientbereich des Anwendungsfensters beschränkt.|  
  
 **Unterstützung für die Dokument\-\/Ansichtarchitektur**  
 Gibt an ob Dokument\-\/Ansichtarchitektur mit der [CDocument Class](../../mfc/reference/cdocument-class.md) und der [CView Class](../../mfc/reference/cview-class.md) \(Standard\) in die Anwendung aufgenommen werden soll.  Deaktivieren Sie dieses Kontrollkästchen, wenn Sie beispielsweise eine MFC\-fremde Anwendung portieren oder die Größe der kompilierten ausführbaren Datei verringern möchten.  Eine Anwendung ohne Dokument\-\/Ansichtarchitektur wird standardmäßig von der [CWinApp Class](../../mfc/reference/cwinapp-class.md) abgeleitet und bietet keine MFC\-Unterstützung für das Öffnen eines Dokuments aus einer Datenträgerdatei.  
  
 **Ressourcensprache**  
 Legt die Sprache Ihrer Ressourcen fest.  In der Liste werden die im System verfügbaren Sprachen angezeigt, so wie sie von Visual Studio installiert wurden.  Wenn Sie eine andere Sprache als die Systemsprache auswählen möchten, muss der entsprechende Vorlagenordner für diese Sprache bereits installiert sein.  Weitere Informationen zur Installation von Sprachressourcen, die von den in der Liste **Ressourcensprache** aufgeführten Standardsprachen abweichen, finden Sie unter [Assistentenunterstützung für andere Sprachen](../../ide/wizard-support-for-other-languages.md).  
  
 Welche Sprache ausgewählt ist, ist anhand der Option **Lokalisierte Zeichenfolgen** auf der Seite [Zeichenfolgen für Dokumentvorlagen, MFC\-Anwendungs\-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md) des Assistenten ersichtlich.  
  
 **Verwenden von Unicode\-Bibliotheken**  
 Gibt an, ob die Unicode\- oder die Nicht\-Unicode\-Version der MFC\-Bibliotheken verwendet wird.  
  
 **Projektstil**  
 Gibt an, ob die Anwendung einen Standard MFC, Datei\-Explorer, Visual Studio oder Office\-Architektur und \-Anzeige hat.  Weitere Informationen finden Sie unter [Erstellen einer MFC\-Anwendung im Stil des Datei\-Explorers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**MFC\-Standard**|Stellt eine Anwendungsarchitektur nach MFC\-Standard bereit.|  
|**Datei\-Explorer**|Implementiert eine Explorer vergleichbare Anwendung die Datei mithilfe eines Splitterfensters an, in dem der linke Bereich [CTreeView Class](../../mfc/reference/ctreeview-class.md) handelt und rechter Bereich [CListView Class](../../mfc/reference/clistview-class.md) ist.|  
|**Visual Studio**|Implementiert eine Visual Studio\-ähnliche Anwendung, die vier andockbare Bereiche enthält \(**Dateiansicht**, **Klassenansicht**, **Eigenschaften** und **Ausgabe**\), die von der [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) abgeleitet werden, sowie ein Hauptrahmenfenster, das von der [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md) abgeleitet wird \(Standard\).|  
|**Office**|Implementiert eine Office\-ähnliche Anwendung, die sowohl ein Menüband beinhaltet, die von der [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) abgeleitet wird, als auch eine Outlook\-Leiste, die von der [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md) abgeleitet wird, eine Titelleiste, die von der [CMFCCaptionBar\-Klasse](../../mfc/reference/cmfccaptionbar-class.md) abgeleitet wird, und einen Hauptrahmen, der von der [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md) abgeleitet wird.|  
  
 **Visueller Stil und Farben**  
 Bestimmt den visuellen Stil der Anwendung.  Die folgenden Optionen sind verfügbar:  
  
-   **Windows systemeigen\/Standard**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 \(blaues Design\)**  
  
-   **Office 2007 \(schwarzes Design\)**  
  
-   **Office 2007 \(silbernes Design\)**  
  
-   **Office 2007 \(aquamarines Design\)**  
  
 **Aktivieren des Wechsels des visuellen Stils**  
 Gibt an, ob der Benutzer den visuellen Stil einer Anwendung zur Laufzeit ändern kann, und zwar üblicherweise durch Auswahl des entsprechenden visuellen Stils aus einem Menü oder von einem Menüband.  
  
 **Verwendung von MFC**  
 Gibt an, wie die Verknüpfung mit der MFC\-Bibliothek erfolgen soll.  MFC wird standardmäßig als gemeinsam genutzte DLL verknüpft.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**MFC in einer gemeinsam genutzten DLL verwenden**|Verknüpft die MFC\-Bibliothek als gemeinsam genutzte DLL mit einer Anwendung.  Die Anwendung sendet zur Laufzeit Aufrufe an die MFC\-Bibliothek.  Durch diese Option benötigen Anwendungen weniger Festplatten\- und Arbeitsspeicherkapazität, wenn sie aus mehreren ausführbaren Dateien zusammengestellt wurden, die die MFC\-Bibliothek nutzen.  Sowohl Win32\- als auch MFC\-Anwendungen können Funktionen in der DLL aufrufen \(Standard\).|  
|**MFC in einer statischen Bibliothek verwenden**|Verknüpft eine Anwendung während der Buildzeit mit der statischen MFC\-Bibliothek.|  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md)