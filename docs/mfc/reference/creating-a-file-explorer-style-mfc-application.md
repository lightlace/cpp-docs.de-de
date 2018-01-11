---
title: "Erstellen die MFC-Anwendung eine Datei-Explorer-ähnliche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfcexplorer.project
dev_langs: C++
helpviewer_keywords:
- browsers [MFC], Explorer-style applications
- MFC applications [MFC], Windows Explorer-style
- Explorer-style applications [MFC], creating
ms.assetid: f843ab5d-2d5d-41ca-88a4-badc0d2f8052
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6098e451b4ebc4caf2bb7fad99ea2e407e4872c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-file-explorer-style-mfc-application"></a>Erstellen einer MFC-Anwendung im Stil des Datei-Explorers
Viele Windows-systemanwendungen verwenden die Benutzeroberfläche (UI) für Datei-Explorer. Wenn Sie die Datei-Explorer starten, sehen Sie z. B. eine Anwendung mit einem vertikalen Teilerleiste, das den Clientbereich. Der linken Seite des Clientbereichs bereitstellt Navigation und Suchfunktionen und der rechten Seite des Clientbereichs zeigt Details im linken Bereich für die Auswahl relevant sind. Klickt ein Benutzer ein Element im linken Bereich, füllt die Anwendung im rechten Bereich aus. Sie können Befehle in einer MDI-Anwendung verwenden, auf die **Ansicht** Menü so ändern Sie die Anzahl der Details im rechten Bereich angezeigt. (In einer SDI- oder Anwendung für mehrere Dokumente der höchsten Ebene können Sie die Details, die mithilfe der Symbolleisten-Schaltflächen ändern.)  
  
 Der Inhalt der Bereiche, hängt von der Anwendung ab. In einem Dateisystem Browser zeigt den linken Bereich eine hierarchische Ansicht von Verzeichnissen, Computer oder Computergruppen, während der rechte Bereich Ordner, einzelne Dateien oder Computer und Einzelheiten zu diesen zeigt. Der Inhalt müssen nicht unbedingt Dateien. Sie können e-Mail-Nachrichten, Fehlerberichte oder andere Elemente in einer Datenbank sein.  
  
 Der Assistent erstellt die folgenden Klassen für Sie:  
  
-   Die **CLeftView** Klasse definiert den linken Bereich des Clientbereichs. Es wird immer von abgeleitet [CTreeView](../../mfc/reference/ctreeview-class.md).  
  
-   Das C*ProjName*View-Klasse definiert den rechten Bereich des Clientbereichs. Wird standardmäßig vom abgeleitet [CListView](../../mfc/reference/clistview-class.md) kann jedoch eine andere Sicht abhängig von der Objektklasse, die Sie angeben, aus der **Basisklasse** in Liste der [generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) auf der Seite der Assistenten.  
  
 Die generierte Anwendung kann eine Einzeldokumentoberfläche (SDI), einer mehrfachen Dokumentschnittstelle (MDI) oder eine Architektur, die mehrere Dokumente der höchsten Ebene aufweisen. Jede Rahmenfenster die Anwendung erstellt wird vertikal geteilt mit [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md). Dieser Anwendungstyp Codierung ähnelt der Codierung einer normalen MFC-Anwendung, die eine Aufteilung verwendet, mit dem Unterschied, dass diese Art von Anwendung separaten Steuerelement Ansichten innerhalb jedes Bereichs Splitter verfügt.  
  
 Wenn Sie die Standardansicht für die Liste im rechten Bereich verwenden, erstellt der Assistent zusätzliche Menüoptionen (in nur für MDI-Anwendungen) und Schaltflächen der Symbolleiste, um die Ansicht Stil große Symbole, kleine Symbole, Liste und Detail-Modi zu wechseln.  
  
### <a name="to-begin-creating-a-file-explorer-style-mfc-executable"></a>Um zu beginnen, erstellen eine ausführbare Datei-Explorer-ähnliche MFC  
  
1.  Befolgen Sie die Anweisungen im [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Im MFC-Anwendungs-Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite der **Datei-Explorer** Projekt Stil.  
  
3.  Legen Sie alle anderen Optionen, die Sie wünschen, auf den anderen Seiten des Assistenten.  
  
4.  Klicken Sie auf **Fertig stellen** um die skelettanwendung zu erzeugen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [Abgeleitete Ansichtsklassen](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)   
 [Erstellen einer formularbasierten MFC-Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md)

