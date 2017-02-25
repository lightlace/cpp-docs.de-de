---
title: "Anwendungsinformationen und Anwendungsverwaltung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [MFC], Verwalten"
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Anwendungsinformationen und Anwendungsverwaltung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Anwendung schreiben, erstellen Sie einzelnen [CWinApp](../../mfc/reference/cwinapp-class.md) abgeleitetes Objekt.  Gelegentlich soll Informationen zum Objekt außerhalb von `CWinApp` abrufen abgeleitetes Objekt.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt die folgenden globalen Funktionen, die Ihnen helfen, diese Aufgaben auszuführen:  
  
### Anwendungsinformations\- und Verwaltungs\-Funktionen  
  
|||  
|-|-|  
|[AfxBeginThread](../Topic/AfxBeginThread.md)|Erstellt einen neuen Thread.|  
|[AfxEndThread](../Topic/AfxEndThread.md)|Beendet den aktuellen Thread.|  
|[AfxFreeLibrary](../Topic/AfxFreeLibrary.md)|Dekrementiert den Verweiszähler des geladenen Dynamic Link Library\-Version \(DLL\)\- Moduls; Wenn der Verweiszähler Null erreicht, wird das Modul die Eigenschaft.|  
|[AfxGetApp](../Topic/AfxGetApp.md)|Gibt einen Zeiger auf das `CWinApp`\-Objekt der Anwendung zurück.|  
|[AfxGetAppName](../Topic/AfxGetAppName.md)|Gibt eine Zeichenfolge zurück, die den Namen der Anwendung enthält.|  
|[AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|Gibt `HINSTANCE` zurück, die diese Instanz der Anwendung darstellt.|  
|[AfxGetMainWnd](../Topic/AfxGetMainWnd.md)|Gibt einen Zeiger auf das aktuelle Fenster "jeweils einer Anwendung NichtOLE oder im direkten Rahmenfenster einer Serveranwendung zurück.|  
|[AfxGetPerUserRegistration](../Topic/AfxGetPerUserRegistration.md)|Verwenden Sie diese Funktion, um zu bestimmen, ob die Anwendung die Registrierung zum Knoten **HKEY\_CURRENT\_USER** \(**HKCU**\) umgeleitet wird.|  
|[AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md)|Gibt `HINSTANCE` \- Quelle die Standardressourcen der Anwendung zurück.  Verwenden Sie diese, um auf die Ressourcen der Anwendung direkt zugreifen.|  
|[AfxGetThread](../Topic/AfxGetThread.md)|Ruft einen Zeiger auf das aktuelle [CWinThread](../../mfc/reference/cwinthread-class.md)\-Objekt ab.|  
|[AfxInitRichEdit](../Topic/AfxInitRichEdit.md)|Initialisiert das Rich\-Edit\-Steuerelement der Version 1.0 für die Anwendung.|  
|[AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md)|Initialisiert die Version 2.0 und höher Rich\-Edit\-Steuerelement für die Anwendung.|  
|[AfxLoadLibrary](../Topic/AfxLoadLibrary.md)|Ordnet ein DLL\-Modul zu und gibt ein Handle zurück, das verwendet werden kann, um die Adresse einer DLL\-Funktion zu erhalten.|  
|[AfxRegisterClass](../Topic/AfxRegisterClass.md)|Registriert eine Fensterklasse in einer DLL, die MFC verwendet.|  
|[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md)|Registriert eine Windows\-Fensterklasse, um zu ergänzen, die automatisch von MFC registriert werden.|  
|[AfxSetPerUserRegistration](../Topic/AfxSetPerUserRegistration.md)|Legt fest, ob die Anwendung die Registrierung zum Knoten **HKEY\_CURRENT\_USER** \(**HKCU**\) umgeleitet wird.|  
|[AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md)|Legt das `HINSTANCE` Handle fest, in dem die Standardressourcen der Anwendung geladen werden.|  
|[AfxSocketInit](../Topic/AfxSocketInit.md)|Wird in einer `CWinApp::InitInstance` \- Überschreibung, um Windows Sockets zu initialisieren.|  
|[AfxWinInit](../Topic/AfxWinInit.md)|Wird von der `WinMain` MFC\-angegebene Funktion, als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) die Initialisierung einer GUI\-basierten Anwendung, MFC zu initialisieren.  Dürfen direkt für Konsolenanwendungen aufgerufen werden, die MFC verwenden.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)