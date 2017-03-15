---
title: "QuickInfos f&#252;r die Symbolleiste | Microsoft Docs"
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
  - "CBRS_FLYBY-Konstante"
  - "CBRS_TOOLTIPS-Konstante"
  - "Schnelle Statusleistenupdates"
  - "Statusleisten, QuickInfos"
  - "QuickInfos [C++]"
  - "QuickInfos [C++], Aktivieren"
  - "QuickInfos [C++], Hinzufügen von Text"
  - "Aktualisierungen"
  - "Aktualisierungen, Statusleistenmeldungen"
  - "Aktualisieren von Statusleistenmeldungen"
ms.assetid: d1696305-b604-4fad-9f09-638878371412
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# QuickInfos f&#252;r die Symbolleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

QuickInfo sind die sehr kleinen Popupfenster, die vorhandene kurzen Beschreibungen den Zweck einer Symbolleisten\-Schaltfläche, wenn Sie die Maus über die Schaltfläche für einen bestimmten Zeitraum positionieren.  Wenn Sie eine Anwendung mit dem Anwendungs\-Assistenten erstellen, der eine Symbolleiste enthält, wird QuickInfounterstützung für Sie bietet.  Dieser Artikel werden sowohl die QuickInfounterstützung, die vom Anwendungs\-Assistenten erstellt wird und wie QuickInfounterstützung der Anwendung hinzugefügt werden.  
  
 Dieser Artikel werden ab:  
  
-   [Aktivieren von QuickInfos](#_core_activating_tool_tips)  
  
-   [Luftparadestatusleistenupdates](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a> Aktivieren von QuickInfos  
 Um QuickInfo in der Anwendung zu aktivieren, müssen Sie folgende Möglichkeiten:  
  
-   Fügen Sie dem Stil `CBRS_TOOLTIPS` verschiedenen Formaten \(wie **WS\_CHILD**, **WS\_VISIBLE**, **CBRS\_** und anderen Formaten\) übergeben der `dwStyle` als Parameter an die [CToolBar::Create](../Topic/CToolBar::Create.md)\-Funktion oder im [SetBarStyle](../Topic/CControlBar::SetBarStyle.md) hinzu.  
  
-   Wie in der folgenden Prozedur beschrieben, fügen Sie den Symbolleistenquickinfo\-text an, getrennt durch ein Zeilenumbruchzeichen \("\\ n "\), der Zeichenfolgenressource, die das Befehlszeilenverlangung den Symbolleistenbefehl enthält.  Die Zeichenfolgenressource Gibt die ID der Symbolleisten\-Schaltfläche frei.  
  
#### So den QuickInfo\-Text hinzufügen  
  
1.  Während Sie die Symbolleiste im Symbolleisten\-Editor bearbeiten, öffnen Sie das **Symbolleistenschaltflächeneigenschaften** angegebene Fenster für eine Schaltfläche.  
  
2.  Im Feld **Eingabeaufforderung**  geben Sie den Text, den Sie in der QuickInfo für die Schaltfläche angezeigt werden soll.  
  
> [!NOTE]
>  Das Festlegen des Texts als Schaltflächeneigenschaft im Symbolleisten\-Editor ersetzt die vorherige Prozedur, in der Sie öffnen mussten und die Zeichenfolgeressource bearbeiten.  
  
 Wenn eine Steuerleiste mit den QuickInfos, die aktiviert werden, die untergeordnete Steuerelemente enthalten, die für sie eingefügt werden, wird die Steuerleiste eine QuickInfo für jedes untergeordnete Steuerelement auf der Steuerleiste an, solange sie die folgenden Kriterien erfüllt:  
  
-   Die ID des Steuerelements befindet nicht. \- 1.  
  
-   Der Eintrag aus einer Zeichenfolgentabelle mit derselben ID wie das untergeordnete Steuerelement in der Ressourcendatei besitzt eine QuickInfo\-Zeichenfolge.  
  
##  <a name="_core_fly_by_status_bar_updates"></a> Luftparade\-Statusleisten\-Updates  
 Eine Funktion, die den QuickInfos verknüpft wird, ist "Luftparade" Statusleistenaktualisieren.  Standardmäßig werden die Meldung auf der Statusleiste nur eine bestimmte Symbolleisten\-Schaltfläche, wenn die Schaltfläche aktiviert ist.  Mit `CBRS_FLYBY` in der Liste von Formatvorlagen enthalten, die an `CToolBar::Create` übergeben werden, können Sie diese Meldungen aktualisieren lassen, wenn der Mauszeiger über die Symbolleiste übergeben, ohne die Schaltfläche tatsächlich zu aktivieren.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [MFC\-Symbolleisten\-Implementierung \(Übersichtsinformationen über Symbolleisten\)](../mfc/mfc-toolbar-implementation.md)  
  
-   [Andockbare und unverankerte Symbolleisten](../mfc/docking-and-floating-toolbars.md)  
  
-   Die Klassen [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)  
  
-   [Arbeiten mit dem ToolBar\-Steuerelement](../mfc/working-with-the-toolbar-control.md)  
  
-   [Mit der alten Symbolleisten](../mfc/using-your-old-toolbars.md)  
  
## Siehe auch  
 [Implementieren der MFC\-Symbolleiste](../mfc/mfc-toolbar-implementation.md)