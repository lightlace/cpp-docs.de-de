---
title: "Arbeiten mit dem Symbolleisten-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CToolBarCtrl-Klasse, Zugreifen auf die Symbolleiste"
  - "GetToolBarCtrl-Methode"
  - "Symbolleisten-Steuerelemente [MFC], Aufrufen"
  - "Symbolleisten [C++], Zugreifen auf allgemeine Steuerelemente"
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Arbeiten mit dem Symbolleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie Sie auf das Objekt [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) zugreifen können, das [CToolBar](../mfc/reference/ctoolbar-class.md) für eine umfassendere Kontrolle den Symbolleisten zugrunde liegt.  Dies ist ein fortgeschrittenes Thema.  
  
## Prozeduren  
  
#### Um auf die Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement zuzugreifen, die dem CToolBar zugrunde liegt \- Objekts  
  
1.  Aufruf [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md).  
  
 `GetToolBarCtrl` gibt einen Verweis auf ein [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)\-Objekt zurück.  Sie können den Verweis auf Aufrufsmemberfunktionen der Symbolleisten\-Steuerelement\-Klasse verwenden.  
  
> [!CAUTION]
>  Während, Funktionen `CToolBarCtrl` ist **Abrufen** aufzurufen, verwenden Vorsicht sicher, wenn Sie die Funktionen **Festlegen**  aufrufen.  Dies ist ein fortgeschrittenes Thema.  Normalerweise sollten Sie nicht auf das zugrunde liegende ToolBar\-Steuerelement zugreifen müssen.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Steuerelemente \(allgemeine Windows\-Steuerelemente\)](../mfc/controls-mfc.md)  
  
-   [Grundlagen zu Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   [Die Symbolleiste dynamisch angepasst wird](../mfc/docking-and-floating-toolbars.md)  
  
-   [QuickInfo in Symbolleisten](../mfc/toolbar-tool-tips.md)  
  
-   [Luftparadestatusleistenupdates](../mfc/toolbar-tool-tips.md)  
  
-   [Behandlungsquickinfobenachrichtigungen](../mfc/handling-tool-tip-notifications.md)  
  
-   Die Klassen [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Behandlungsanpassungsbenachrichtigungen](../mfc/handling-customization-notifications.md)  
  
-   [Mehrere Symbolleisten](../mfc/toolbar-fundamentals.md)  
  
-   [Mit der alten Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
 Allgemeine Informationen über die Anwendung der allgemeinen Windows\-Steuerelemente, finden Sie unter [Allgemeine Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493).  
  
## Siehe auch  
 [Implementieren der MFC\-Symbolleiste](../mfc/mfc-toolbar-implementation.md)