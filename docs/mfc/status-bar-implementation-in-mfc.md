---
title: "Implementieren der Statusleiste mit MFC"
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
  - "COldStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COldStatusBar-Klasse"
  - "CStatusBar-Klasse, und CStatusBarCtrl-Klasse"
  - "CStatusBar-Klasse, und MFC-Statusleisten"
  - "CStatusBarCtrl-Klasse, und CStatusBar-Klasse"
  - "CStatusBarCtrl-Klasse, und MFC-Statusleisten"
  - "Statusleisten, und CStatusBarCtrl-Klasse"
  - "Statusleisten, Abwärtskompatibilität"
  - "Statusleisten, Implementieren in MFC"
  - "Statusleisten, alt mit COldStatusBar-Klasse"
  - "Statusleisten, Windows 95-Implementierung"
  - "Statusindikatoren"
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Implementieren der Statusleiste mit MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein [CStatusBar](../mfc/reference/cstatusbar-class.md)\-Objekt ist eine Steuerleiste mit einer Zeile von Textausgabebereichen.  Die Ausgabebereiche sind als Meldungszeilen und als Statusanzeigen häufig verwendet.  Beispiele hierfür sind die Menühilfemeldungszeilen, die kurz den ausgewählten Menübefehl erläutern und die Indikatoren, die den Status ROLLENs anzeigen, NUM\- und anderes verschlüsselt.  
  
 Seit MFC 4.0, werden Statusleisten mit der Klasse [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) implementiert, die eine Statusleistengemeinsame allgemeinen ToolTip\-Steuerelement kapselt.  Um Rückwärtskompatibilität entscheidet nun MFC die ältere Statusleistenimplementierung in Klasse **COldStatusBar** bei.  Die Dokumentation für ältere Versionen von MFC wird **COldStatusBar** unter `CStatusBar`.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), eine Memberfunktion, die MFC 4.0 neu ist, können Sie, um die Unterstützung des allgemeinen Windows\-Steuerelements für Statusleistenanpassung und \-zusätzliche Funktionen zu nutzen.  `CStatusBar`\-Memberfunktionen geben Sie alle Funktionen der allgemeinen Windows\-Steuerelemente; Wenn Sie jedoch `GetStatusBarCtrl` aufrufen, können Sie auf StatusBar\-Steuerelemente noch mehr der Eigenschaften einer Statusleiste geben.  Wenn Sie `GetStatusBarCtrl` aufrufen, wird ein Verweis auf ein `CStatusBarCtrl`\-Objekt zurück.  Sie können diesen Verweis verwenden, um das StatusBar\-Steuerelement zu bearbeiten.  
  
 Die folgende Abbildung zeigt eine Statusleiste an, die verschiedene Indikatoren angezeigt.  
  
 ![Statusleiste](../mfc/media/vc37dy1.png "vc37DY1")  
Statusleiste  
  
 Wie die Symbolleiste wird das Statusleistenobjekt in das übergeordnete Rahmenfenster eingebettet und wird automatisch erstellt, wenn das Rahmenfenster erstellt wird.  Die Statusleiste, wie alle Steuerleisten, wird auch automatisch zerstört, wenn die übergeordnete Frame zerstört werden.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Aktualisieren des Text eines Statusleistenbereichs](../mfc/updating-the-text-of-a-status-bar-pane.md)  
  
-   MFC\-Klassen [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [Dialogleisten](../mfc/dialog-bars.md)  
  
-   [Symbolleisten \(MFC\-Symbolleisten\-Implementierung\)](../mfc/mfc-toolbar-implementation.md)  
  
## Siehe auch  
 [Statusleisten](../mfc/status-bars.md)