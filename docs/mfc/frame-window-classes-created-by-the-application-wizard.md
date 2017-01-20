---
title: "Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen"
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
  - "CMainFrame"
  - "CMainFrame::PreCreateWindow"
  - "CMainFrame.PreCreateWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], Rahmenfensterklassen, erstellt von"
  - "CFrameWnd-Klasse, Rahmenfenster"
  - "Klassen [C++], Rahmenfenster"
  - "CMainFrame-Klasse"
  - "CMDIChildWnd-Klasse, Rahmenfenster"
  - "CMDIFrameWnd-Klasse, Rahmenfenster"
  - "Rahmenfensterklassen, Erstellt mit Anwendungs-Assistenten"
  - "Fensterklassen"
  - "Fensterklassen, Rahmen"
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
caps.latest.revision: 8
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie [Anwendungs\-Assistent](../ide/creating-desktop-projects-by-using-application-wizards.md) verwenden, um ein Anwendungsskelett, sowie zur Anwendung, z Dokument und der Ansichtsklassen zu erstellen, erstellt der Anwendungs\-Assistent eine abgeleitete Rahmenfensterklasse für das Hauptrahmenfenster der Anwendung.  Die Klasse wird standardmäßig `CMainFrame` aufgerufen, und die Dateien, die es enthalten, werden MAINFRM.H und MAINFRM.CPP benannt.  
  
 Wenn die SDI\-Anwendung ist, wird die Klasse `CMainFrame` von der [CFrameWnd](../mfc/reference/cframewnd-class.md) abgeleitet.  
  
 Wenn die Anwendung auch MDI\-Anwendungen ist, wird `CMainFrame` von der Klasse [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) abgeleitet.  In diesem Fall implementiert `CMainFrame` des Hauptframes, der das Menü, Symbolleiste und die Statusleisten enthält.  Der Anwendungs\-Assistent abgeleitet keine neue Dokumentrahmenfensterklasse für Sie.  Stattdessen wird die Standardimplementierung in [CMDIChildWnd\-Klasse](../mfc/reference/cmdichildwnd-class.md).  Das MFC\-Framework stellt ein untergeordnetes Fenster, um jede Ansicht die \(usw. zu enthalten vom Typ `CScrollView`, `CEditView`, `CTreeView`, `CListView` sein kann\), das die Anwendung benötigt.  Wenn Sie ein Dokumentrahmenfenster anpassen müssen, können Sie eine neue Dokumentrahmenfensterklasse erstellen \(siehe [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)\).  
  
 Wenn Sie festlegen, um eine Symbolleiste zu unterstützen, verfügt die Klasse zusätzlich die Membervariablen des Typs [CToolBar](../mfc/reference/ctoolbar-class.md) und [CStatusBar](../mfc/reference/cstatusbar-class.md) und der `OnCreate` Meldungshandlerfunktion, um zwei [Steuerleisten](../mfc/control-bars.md) initialisieren.  
  
 Diese Rahmenfensterklassen arbeiten, z erstellt, aber, ihre Funktionalität zu erweitern, müssen Sie und Membervariablen Memberfunktionen hinzu.  Sie sollten auch die Fensterklassen andere Windows\-Meldungen bearbeiten können.  Weitere Informationen finden Sie unter [Die Formate eines Fensters geändert wird von MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## Siehe auch  
 [Rahmenfensterklassen](../mfc/frame-window-classes.md)   
 [MFC\-Programm oder Steuern von Quell\- und Headerdateien](../ide/mfc-program-or-control-source-and-header-files.md)