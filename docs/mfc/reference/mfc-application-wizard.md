---
title: MFC-Anwendung-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4cbdc5e6db53fd4eacf9154bc356a1a64c77391
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372002"
---
# <a name="mfc-application-wizard"></a>MFC-Anwendungs-Assistent
Der MFC-Anwendungs-Assistent erstellt eine Anwendung, die beim Kompilieren die grundlegenden Funktionen einer ausführbaren Windows-Anwendung (.exe) implementiert. Die MFC-Startanwendung umfasst C++-Quelldateien (.cpp), Ressourcendateien (.rc), Headerdateien (.h) sowie eine Projektdatei (.vcxproj). Der in diesen Startdateien generierte Code basiert auf MFC.  
  
> [!NOTE]
>  Abhängig von den ausgewählten Optionen kann der Assistent zusätzliche Projektdateien erstellen. Angenommen, Sie wählen **kontextbezogene Hilfe** auf die [erweiterte Funktionen](../../mfc/reference/advanced-features-mfc-application-wizard.md) Seite der Assistent erstellt die Dateien, die zum Kompilieren von Hilfedateien für das Projekt erforderlich sind. Weitere Informationen zu Dateien, die der Assistent erstellt, finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md), und finden Sie im Projekt die Datei "Readme.txt".  
  
## <a name="overview"></a>Übersicht  
 Auf dieser Seite des Assistenten sind die aktuellen Anwendungseinstellungen für die zu erstellende MFC-Anwendung aufgeführt. Der Assistent erstellt ein Projekt standardmäßig wie folgt:  
  
-   [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   Das Projekt wird mit MDI (Multiple Document Interface)-Unterstützung mit Registerkarten erstellt. Weitere Informationen finden Sie unter [SDI und MDI](../../mfc/sdi-and-mdi.md).  
  
    -   Das Projekt verwendet die [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md).  
  
    -   Das Projekt verwendet Unicode-Bibliotheken.  
  
    -   Das Projekt wird mit dem Visual Studio-Projektformat erstellt und aktiviert visuelles Stilswitching.  
  
    -   Das Projekt verwendet MFC in einer gemeinsam genutzten DLL. Weitere Informationen finden Sie unter [DLLs in Visual C++](../../build/dlls-in-visual-cpp.md).  
  
-   [Verbunddokumentunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   Das Projekt bietet keine Unterstützung für Verbunddokumente.  
  
-   [Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   Das Projekt verwendet den Projektnamen als standardmäßige Zeichenfolgen für Dokumentvorlagen.  
  
-   [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   Das Projekt bietet keine Datenbankunterstützung.  
  
-   [Benutzeroberflächen-Funktionen, MFC-Anwendungs-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   Das Projekt implementiert die standardmäßigen Windows-Benutzeroberflächen-Funktionen wie z. B. ein Systemmenü, eine Statusleiste, Systemmenü minimieren und maximieren, ein **zu** Feld, eine Standardmenüleiste und andockbare Symbolleiste sowie untergeordnete Rahmen.  
  
-   [Erweiterte Funktionen, MFC-Anwendungs-Assistent](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   Das Projekt unterstützt das Drucken und die Seitenansicht.  
  
    -   Das Projekt unterstützt ActiveX-Steuerelemente. Weitere Informationen finden Sie unter [Sequenz der Vorgänge zum Erstellen von ActiveX-Steuerelemente](../../mfc/sequence-of-operations-for-creating-activex-controls.md).  
  
    -   Das Projekt bietet keine Unterstützung für [Automatisierung](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), oder Active Accessibility.  
  
    -   Das Projekt unterstützt eine **Explorer** andockbaren Bereich, ein **Ouput** andockbaren Bereich, und ein **Eigenschaften** andockbaren Bereich.  
  
-   [Erstellte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   Das Projekt View-Klasse abgeleitet ist die [CView-Klasse](../../mfc/reference/cview-class.md).  
  
    -   Das Projekt Anwendungsklasse stammt aus der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md).  
  
    -   Das Projekt Dokumentklasse stammt aus dem [CDocument-Klasse](../../mfc/reference/cdocument-class.md).  
  
    -   Das Projekt Hauptframe-Klasse abgeleitet ist die [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md).  
  
    -   Das Projekt untergeordnete Klasse stammt aus dem [CMDIChildWndEx-Klasse](../../mfc/reference/cmdichildwndex-class.md).  
  
 Um diese Standardeinstellungen zu ändern, klicken Sie in der linken Spalte des Assistenten auf die Titel der entsprechenden Registerkarten und nehmen auf der angezeigten Seite die Änderungen vor.  
  
 Nachdem Sie ein MFC-Anwendungsprojekt erstellen, können Sie hinzufügen Objekte oder Steuerelemente zum Projekt mit Visual C++ [-code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Mfc_anwendung](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)   
 [Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
