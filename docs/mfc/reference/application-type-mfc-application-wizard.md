---
title: Anwendungstyp, MFC-Anwendungs-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.apptype
dev_langs:
- C++
helpviewer_keywords:
- static libraries, MFC
ms.assetid: c3f62b0e-3f13-42c5-9859-d3890d0c3e1d
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: bd862d4a537f2297c1ee5a6fd517e22f7c684fa4
ms.contentlocale: de-de
ms.lasthandoff: 04/01/2017

---
# <a name="application-type-mfc-application-wizard"></a>Anwendungstyp, MFC-Anwendungs-Assistent
Mithilfe dieser Seite des der [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md) zu entwerfen und grundlegende Funktionen zu einer neuen MFC-Anwendung hinzuzufügen.  
  
 **Anwendungstyp**  
 Gibt den Typ der dokumentunterstützung, die Sie in Ihrer Anwendung erstellen möchten. Die Art der Anwendung, die Sie auswählen, bestimmt die Optionen der Benutzeroberfläche, die für Ihre Anwendung verfügbar sind. Finden Sie unter [Benutzeroberflächen-Features, MFC-Anwendungs-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md) für Weitere Informationen.  
  
 Weitere Informationen zu den Typen von Dokumenten finden Sie unter:  
  
-   [SDI und MDI](../../mfc/sdi-and-mdi.md)  
  
-   [Rahmenfenster](../../mfc/frame-windows.md)  
  
-   [Rahmenfensterklassen](../../mfc/frame-window-classes.md)  
  
-   [Dokumente, Ansichten und das Framework](../../mfc/documents-views-and-the-framework.md)  
  
-   [Dialogfelder](../../mfc/dialog-boxes.md)  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Einzelnes Dokument**|Erstellt eine single Document Interface (SDI)-Architektur für Ihre Anwendung, in dem anhand eine Ansichtsklasse [CView-Klasse](../../mfc/reference/cview-class.md). Sie können die Basisklasse für die Ansicht im Ändern der [generierte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten. Um eine formularbasierte Anwendung zu erstellen, verwenden Sie z. B. [CFormView-Klasse](../../mfc/reference/cformview-class.md) für die Ansichtsklasse.<br /><br /> Bei dieser Art von Anwendung kann die Dokumentrahmenfenster nur ein einzelnes Dokument enthalten.|  
|**Mehrere Dokumente**|Erstellt eine multiple Document Interface (MDI)-Architektur für Ihre Anwendung, in dem anhand eine Ansichtsklasse `CView`. Sie können die Basisklasse für die Ansicht im Ändern der **generierte Klassen** Seite des Assistenten. Um eine formularbasierte Anwendung zu erstellen, verwenden Sie z. B. `CFormView` für die Ansichtsklasse.<br /><br /> Bei dieser Art von Anwendung kann die Dokumentrahmenfenster mehrere untergeordnete Fenster enthalten.|  
|**Dokumente im Registerformat**|Platziert jedes Dokument auf einer separaten Registerkarte an.|  
|**Dialogfeld basierend**|Erstellt eine auf Dialogfeldern basierende Architektur für Ihre Anwendung, in dem anhand eine Dialogfeldklasse `CDialog`. (Um ein HTML-Dialogfeld zu erstellen, aktivieren Sie das **HTML-Dialogfeld verwenden**.)|  
|**Verwenden Sie HTML-Dialogfeld**|Dialogfeld Feld nur für Anwendungen. Leitet die Dialogfeldklasse von [CDHtmlDialog Klasse](../../mfc/reference/cdhtmldialog-class.md) anstelle von [CDialog-Klasse](../../mfc/reference/cdialog-class.md). Wenn Sie dieses Kontrollkästchen `CDHtmlDialog` abgelesen werden die **Basisklasse** Feld der [generierte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten.<br /><br /> Ein `CDHtmlDialog`-abgeleitetes Dialogfeld zeigt HTML-basierte Dialogfelder an, den Austausch von Daten mit HTML-Steuerelemente sowie die HTML-Ereignisse behandelt.|  
|**Mehrere Dokumente der höchsten Ebene**|Erstellt eine Architektur, die mehrere der obersten Ebene für Ihre Anwendung, in dem anhand eine Ansichtsklasse `CView`.<br /><br /> Bei dieser Art der Anwendung, wenn ein Benutzer klickt **neu** (oder **neue Frame**) auf die **Datei** im Menü die Anwendung erstellt ein Fenster, dessen übergeordnetes Element implizit den Desktop ist. Der neue Dokumentrahmen wird in der Taskleiste angezeigt und ist nicht darauf beschränkt, das den Clientbereich des Anwendungsfensters.|  
  
 **Dokument-/Ansichtarchitektur Architektur-Unterstützung**  
 Gibt an, ob Dokument-/Ansichtarchitektur in Ihrer Anwendung mithilfe der [CDocument-Klasse](../../mfc/reference/cdocument-class.md) und [CView-Klasse](../../mfc/reference/cview-class.md) (Standard). Deaktivieren Sie dieses Kontrollkästchen, wenn Sie eine MFC-fremde Anwendung portieren, oder wenn Sie die kompilierte ausführbare Datei verkleinern möchten. Standardmäßig wird von eine Anwendung ohne Dokument-/Ansichtarchitektur abgeleitet [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md), und es umfasst nicht die MFC-Unterstützung für das Öffnen eines Dokuments von einer Datenträgerdatei.  
  
 **Ressourcensprache**  
 Hiermit wird die Sprache Ihrer Ressourcen. Die Liste enthält die verfügbaren Sprachen auf Ihrem System an, wie vom Visual Studio installiert. Wenn Sie eine andere Sprache als der Systemsprache auswählen möchten, muss der entsprechende Vorlagenordner für diese Sprache bereits installiert sein. Weitere Informationen zum Installieren von Sprachressourcen, die sich von den Standardwerten, die zur Verfügung, in der **Ressourcensprache** auflisten, finden Sie unter [Assistentenunterstützung für andere Sprachen](../../ide/wizard-support-for-other-languages.md).  
  
 Die Sprache, die Sie auswählen, wirkt sich die **lokalisierte Zeichenfolgen** -Option von der [Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md) Seite des Assistenten.  
  
 **Verwenden von Unicode-Bibliotheken**  
 Gibt an, ob die Unicode oder nicht-Unicode-Version der MFC-Bibliotheken verwendet wird.  
  
 **Projektstil**  
 Gibt an, ob Ihre Anwendung ein standard MFC, Datei-Explorer, Visual Studio oder Office-Architektur und Anzeige verfügt. Weitere Informationen finden Sie unter [erstellen die MFC-Anwendung eine Datei-Explorer-ähnliche](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md).  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**MFC-standard**|Stellt eine standardmäßige MFC-Anwendungsarchitektur bereit.|  
|**Datei-Explorer**|Implementiert eine Datei-Explorer-ähnlichen Anwendung mit einem Splitterfenster, in dem der linke Bereich ist, eine [CTreeView-Klasse](../../mfc/reference/ctreeview-class.md) und der rechte Bereich ist eine [CListView-Klasse](../../mfc/reference/clistview-class.md).|  
|**Visual Studio**|Implementiert eine Visual Studio-ähnliche-Anwendung, die vier andockbare Bereiche enthält (**Dateiansicht**, **Klassenansicht**, **Eigenschaften**, und **Ausgabe**), die abgeleitet sind [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) und einem Hauptrahmenfenster, die abgeleitet ist [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md) (Standard).|  
|**Office**|Implementiert eine Office-ähnliche-Anwendung, die ein Menüband enthält, die abgeleitet ist [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md), eine Outlook-Leiste, die abgeleitet ist [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md), eine Titelleiste, die abgeleitet ist [CMFCCaptionBar-Klasse](../../mfc/reference/cmfccaptionbar-class.md), und eine Hauptframe, die abgeleitet ist [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md).|  
  
 **Visueller Stil und Farben**  
 Bestimmt den visuellen Stil der Anwendung an. Die folgenden Optionen sind verfügbar:  
  
-   **Windows-systemeigenen/Standard**  
  
-   **Office 2003**  
  
-   **Visual Studio 2005**  
  
-   **Office 2007 (blaues Design)**  
  
-   **Office 2007 (schwarze Design)**  
  
-   **Office 2007 (Design "Silber")**  
  
-   **Office 2007 (Aqua Design)**  
  
 **Aktivieren Sie visuelle stilumschaltung**  
 Gibt an, ob der Benutzer den visuellen Stil der Anwendung zur Laufzeit in der Regel ändern kann durch Auswählen der geeigneten visuellen Stils aus einem Menü oder das Menüband.  
  
 **Verwendung von MFC**  
 Gibt an, wie mit der MFC-Bibliothek zu verknüpfen. MFC ist standardmäßig als eine freigegebene DLL verknüpft.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**MFC in einer gemeinsam genutzten DLL verwenden**|Die MFC-Bibliothek verknüpft mit einer Anwendung als eine freigegebene DLL. Die Anwendung ruft die MFC-Bibliothek zur Laufzeit. Diese Option verringert die Festplatten- und Anforderungen von Anwendungen, die aus mehreren ausführbaren Dateien bestehen, die die MFC-Bibliothek verwenden. Win32- und MFC-Anwendungen können Funktionen in der DLL (Standard) aufrufen.|  
|**Verwenden von MFC in einer statischen Bibliothek**|Verknüpft eine Anwendung mit der statischen MFC-Bibliothek zur Buildzeit.|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md)


