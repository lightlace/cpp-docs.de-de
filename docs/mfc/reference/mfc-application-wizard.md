---
title: MFC-Anwendungs-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.overview
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
ms.openlocfilehash: 3cdaba750060290fa25007d4097b6782d6f20fbf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258631"
---
# <a name="mfc-application-wizard"></a>MFC-Anwendungs-Assistent

Der MFC-Anwendungs-Assistent erstellt eine Anwendung, die beim Kompilieren die grundlegenden Funktionen einer ausführbaren Windows-Anwendung (.exe) implementiert. Die MFC-Startanwendung umfasst C++-Quelldateien (.cpp), Ressourcendateien (.rc), Headerdateien (.h) sowie eine Projektdatei (.vcxproj). Der in diesen Startdateien generierte Code basiert auf MFC.

> [!NOTE]
>  Abhängig von den ausgewählten Optionen kann der Assistent zusätzliche Projektdateien erstellen. Wenn Sie auswählen, z. B. **kontextbezogene Hilfe** auf die [erweiterte Features](../../mfc/reference/advanced-features-mfc-application-wizard.md) Seite der Assistent erstellt die Dateien, die zum Kompilieren des Projekts Hilfedateien erforderlich sind. Weitere Informationen zu den Dateien, die der Assistent erstellt, finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md), und finden Sie in der Datei "Readme.txt" im Projekt.

## <a name="overview"></a>Übersicht

Auf dieser Seite des Assistenten sind die aktuellen Anwendungseinstellungen für die zu erstellende MFC-Anwendung aufgeführt. Der Assistent erstellt ein Projekt standardmäßig wie folgt:

- [Anwendungstyp, MFC-Anwendungs-Assistent](../../mfc/reference/application-type-mfc-application-wizard.md)

   - Das Projekt wird mit MDI (Multiple Document Interface)-Unterstützung mit Registerkarten erstellt. Weitere Informationen finden Sie unter [SDI und MDI](../../mfc/sdi-and-mdi.md).

   - Das Projekt verwendet die [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md).

   - Das Projekt verwendet Unicode-Bibliotheken.

   - Das Projekt wird mit dem Visual Studio-Projektformat erstellt und aktiviert visuelle Stilumschaltung.

   - Das Projekt verwendet MFC in einer gemeinsam genutzten DLL. Weitere Informationen finden Sie unter [DLLs in Visual C++](../../build/dlls-in-visual-cpp.md).

- [Verbunddokumentunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/compound-document-support-mfc-application-wizard.md)

   - Das Projekt bietet keine Unterstützung für Verbunddokumente.

- [Zeichenfolgen für Dokumentvorlagen, MFC-Anwendungs-Assistent](../../mfc/reference/document-template-strings-mfc-application-wizard.md)

   - Das Projekt verwendet den Projektnamen als standardmäßige Zeichenfolgen für Dokumentvorlagen.

- [Datenbankunterstützung, MFC-Anwendungs-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)

   - Das Projekt bietet keine Datenbankunterstützung.

- [Benutzeroberflächen-Funktionen, MFC-Anwendungs-Assistent](../../mfc/reference/user-interface-features-mfc-application-wizard.md)

   - Das Projekt implementiert die standardmäßigen Windows-Benutzeroberflächen-Funktionen wie z. B. ein Systemmenü, eine Statusleiste, minimieren, und Maximieren ein **zu** Feld, eine Standardmenüleiste und andockbare Symbolleiste sowie untergeordnete Rahmen.

- [Erweiterte Funktionen, MFC-Anwendungs-Assistent](../../mfc/reference/advanced-features-mfc-application-wizard.md)

   - Das Projekt unterstützt das Drucken und die Seitenansicht.

   - Das Projekt unterstützt ActiveX-Steuerelemente. Weitere Informationen finden Sie unter [Sequenz der Vorgänge für ActiveX-Steuerelemente erstellen](../../mfc/sequence-of-operations-for-creating-activex-controls.md).

   - Das Projekt bietet keine Unterstützung für [Automation](../../mfc/automation.md), [MAPI](../../mfc/mapi-support-in-mfc.md), [Windows Sockets](../../mfc/windows-sockets-in-mfc.md), oder Active Accessibility.

   - Das Projekt unterstützt einen **Explorer** andockbaren Bereich, einer **Ausgabe** andockbaren Bereich, und ein **Eigenschaften** andockbaren Bereich.

- [Erstellte Klassen, MFC-Anwendungs-Assistent](../../mfc/reference/generated-classes-mfc-application-wizard.md)

   - Ansichtsklasse des Projekts ergibt sich aus der [CView-Klasse](../../mfc/reference/cview-class.md).

   - Anwendungsklasse des Projekts ergibt sich aus der [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md).

   - Dokumentklasse des Projekts ergibt sich aus der [CDocument-Klasse](../../mfc/reference/cdocument-class.md).

   - Die Hauptrahmenklasse des Projekts ergibt sich aus der [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md).

   - Untergeordnete Klasse des Projekts ergibt sich aus der [CMDIChildWndEx-Klasse](../../mfc/reference/cmdichildwndex-class.md).

Um diese Standardeinstellungen zu ändern, klicken Sie in der linken Spalte des Assistenten auf die Titel der entsprechenden Registerkarten und nehmen auf der angezeigten Seite die Änderungen vor.

Nachdem Sie ein MFC-Anwendungsprojekt erstellen, können Sie hinzufügen Objekte oder Steuerelemente zu Ihrem Projekt mithilfe von Visual C++ [-code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="see-also"></a>Siehe auch

[Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md)<br/>
[MFC-Desktopanwendungen](../../mfc/mfc-desktop-applications.md)<br/>
[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../../mfc/using-the-classes-to-write-applications-for-windows.md)
