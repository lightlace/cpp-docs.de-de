---
title: Symbolleisten-QuickInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 248c975c51a2f44f6c9b17094d6b05082a9016a8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-tool-tips"></a>QuickInfos für die Symbolleiste
QuickInfos sind die kleine Popupfenster, die kurze Beschreibungen der Zweck einer Symbolleisten-Schaltfläche darstellen, wenn die Maus über eine Schaltfläche für eine bestimmte Zeitspanne zu positionieren. Wenn Sie eine Anwendung mit dem Assistenten zum Erstellen, die eine Symbolleiste aufweist, wird für Sie Tipp Toolsupport bereitgestellt. Dieser Artikel beschreibt beide den Tipp Toolsupport erstellt, indem der Anwendungs-Assistent und wie Ihre Anwendung Tipp Toolsupport hinzugefügt.  
  
 Dieser Artikel behandelt:  
  
-   [Aktivieren von QuickInfos](#_core_activating_tool_tips)  
  
-   [Statusleistenupdates](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a>Aktivieren von QuickInfos  
 Um QuickInfos in Ihrer Anwendung zu aktivieren, müssen Sie zwei Schritte ausführen:  
  
-   Hinzufügen der `CBRS_TOOLTIPS` Stil in die anderen Formate (z. B. **WS_CHILD**, **WS_VISIBLE**, und andere **CBRS_** Stile) übergeben, als die `dwStyle` Parameter an die [ Symbolleistenformate](../mfc/reference/ctoolbar-class.md#create) Funktion oder im [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle).  
  
-   Wie im folgenden Verfahren beschrieben wird, fügen Sie die Symbolleiste QuickInfo-Text, getrennt durch ein neue Zeilenvorschubzeichen ("\n"), um eine Zeichenfolgenressource mit der Eingabeaufforderung für die Befehle der Hilfesymbolleiste. Eine Zeichenfolgenressource teilt die ID der Symbolleisten-Schaltfläche.  
  
#### <a name="to-add-the-tool-tip-text"></a>So fügen Sie den QuickInfo-Text hinzu  
  
1.  Während Sie die Symbolleiste im Symbolleisten-Editor bearbeiten, öffnen Sie die **Eigenschaften von Symbolleisten-Schaltfläche** Fenster für die angegebene Schaltfläche.  
  
2.  In der **Prompt** Feld, geben Sie den Text in der QuickInfo für die Schaltfläche angezeigt werden sollen.  
  
> [!NOTE]
>  Festlegen des Texts, wie eine Schaltflächeneigenschaft in der Symbolleisten-Editor das vorherige Verfahren Sie mussten ersetzt um öffnen Sie und bearbeiten Sie eine Zeichenfolgenressource.  
  
 Falls eine Steuerleiste mit QuickInfos aktiviert untergeordnete Steuerelemente, die darauf platziert aufweist, wird die Steuerleiste eine QuickInfo für jedes untergeordnete Steuerelement in der Steuerleiste angezeigt, solange sie die folgenden Kriterien erfüllt:  
  
-   Die ID des Steuerelements ist nicht - 1.  
  
-   Der Zeichenfolgentabelle Eintrag mit derselben ID wie das untergeordnete Steuerelement in der Ressourcendatei verfügt über ein Tool QuickInfo-Zeichenfolge.  
  
##  <a name="_core_fly_by_status_bar_updates"></a>Statusleiste Flyby Updates  
 Eine Funktion, die im Zusammenhang mit QuickInfos ist "Flyby" Statusleiste aktualisieren. Standardmäßig beschreibt die Nachricht auf der Statusleiste nur eine bestimmte Symbolleisten-Schaltfläche, wenn die Schaltfläche aktiviert ist. Dazu `CBRS_FLYBY` in der Liste der Stile an übergeben `CToolBar::Create`, dass diese Nachrichten aktualisiert, wenn der Mauszeiger über der Symbolleiste bewegt wird, ohne tatsächlich aktiviert die Schaltfläche "".  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Implementieren der MFC-Symbolleiste (Übersicht die Übersichtsinformationen auf der Symbolleiste)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   Die [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Klassen  
  
-   [Arbeiten mit dem Toolbar-Steuerelement](../mfc/working-with-the-toolbar-control.md)  
  
-   [Verwenden der bisherigen Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der MFC-Symbolleiste](../mfc/mfc-toolbar-implementation.md)

