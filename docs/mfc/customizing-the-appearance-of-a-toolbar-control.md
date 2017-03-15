---
title: "Anpassen der Darstellung eines Symbolleisten-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBSTYLE_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBar-Klasse, Stile"
  - "CToolBarCtrl-Klasse, Objektstile"
  - "Flache Symbolleisten"
  - "TBSTYLE_-Stile"
  - "Symbolleisten-Steuerelemente [MFC], Stile"
  - "Transparente Symbolleisten"
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Anpassen der Darstellung eines Symbolleisten-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CToolBarCtrl`\-Klasse stellt viele Formate, die das Aussehen \(und gelegentlich das Verhalten\) des Symbolleistenobjekts beeinflussen.  Ändern Sie das Symbolleistenobjekt, indem Sie den `dwCtrlStyle`\-Parameter der Memberfunktion `CToolBarCtrl::Create` \(oder `CToolBar::CreateEx`\) festlegen, wenn Sie zuerst das ToolBar\-Steuerelement erstellen.  
  
 Die folgenden Formate beeinflussen den "3D\-" Aspekt der Symbolleisten\-Schaltflächen und Platzierung des Schaltflächentexts:  
  
-   **TBSTYLE\_FLAT** stellt eine flache Symbolleiste erstellt, in der die Symbolleiste und Schaltflächen transparent sind.  Schaltflächentext wird unter Schaltflächenbitmaps.  Ist dieses Format verwendet wird, wird die Schaltfläche mit den Cursor automatisch hervorgehoben.  
  
-   **TBSTYLE\_TRANSPARENT** stellt eine transparente Symbolleiste erstellt.  In einer transparenten Symbolleiste ist die Symbolleiste transparent, die Schaltflächen sind nicht.  Schaltflächentext wird unter Schaltflächenbitmaps.  
  
-   **TBSTYLE\_LIST** Stellen Schaltfläche Text auf der rechten Seite der Schaltflächenbitmaps.  
  
> [!NOTE]
>  Um zu verhindern zeichnen Sie Probleme, neu **TBSTYLE\_FLAT** und **TBSTYLE\_TRANSPARENT** festgelegt werden Formate dürfen bevor das Symbolleistenobjekt sichtbar ist.  
  
 Die folgenden Formate bestimmen, wenn die Symbolleiste einem Benutzer ermöglicht, um einzelne Schaltflächen innerhalb eines Symbolleistenobjekts mithilfe von Drag & Drop neu anzuordnen:  
  
-   **TBSTYLE\_ALTDRAG** ermöglicht es Benutzern, die die Position einer Symbolleisten\-Schaltfläche ändern, indem er beim Ziehen die ALT\-TASTE gedrückt halten.  Wenn dieser Stil nicht angegeben wird, muss der Benutzer beim Ziehen einer Schaltfläche UMSCHALTTASTE gedrückt halten.  
  
    > [!NOTE]
    >  Das `CCS_ADJUSTABLE` Format muss angegeben werden, um zu ziehende Symbolleisten\-Schaltflächen zu aktivieren.  
  
-   **TBSTYLE\_REGISTERDROP** generiert **TBN\_GETOBJECT** Benachrichtigungsmeldungen, um Ablagezielobjekte bitten, wenn der Mauszeiger auf Symbolleisten\-Schaltflächen übergibt.  
  
 Die anderen Formate beeinflussen visuelles und nicht visuelle Aspekte der Symbolleiste \- Objekts:  
  
-   `TBSTYLE_WRAPABLE` stellt eine Symbolleiste erstellt, die mehrere Zeilen von Schaltflächen verfügen kann.  Symbolleistenschaltflächen ausführen "Wrapper" zur nächsten Zeile ein, wenn die Symbolleiste zu schmal ist, dass alle Schaltflächen auf derselben Zeile aufzunehmen.  Umschließen tritt auf Trennungs\- und nongroupgrenzen auf.  
  
-   **TBSTYLE\_CUSTOMERASE NM\_CUSTOMDRAW** Benachrichtigungsmeldungen generiert, wenn `WM_ERASEBKGND` Meldungen verarbeitet.  
  
-   `TBSTYLE_TOOLTIPS` erstellt ein QuickInfo\-Steuerelement, das eine Anwendung verwenden kann, um beschreibenden Text für die Schaltflächen in der Symbolleiste anzuzeigen.  
  
 Eine vollständige Auflistung der Symbolleistenformaten und \-erweiterten Formaten, finden Sie unter [Symbolleisten\-Steuerelement\- und Schaltflächen\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb760439) und [Symbolleisten\-erweiterte Formate](http://msdn.microsoft.com/library/windows/desktop/bb760430) in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)