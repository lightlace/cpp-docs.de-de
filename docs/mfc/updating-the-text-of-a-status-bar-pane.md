---
title: Aktualisieren des Textes in der eine Statusleiste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fb0f9bdaa032340256eee4781bfd775767f62ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>Aktualisieren des Textes in der Statusleiste
In diesem Artikel wird erläutert, wie zum Ändern des Texts, die in einer MFC-Status-Leistenbereich angezeigt wird. Eine Statusleiste – ein Fensterobjekt der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) – enthält mehrere "Bereiche". Jeder Bereich ist eine rechteckige Fläche der Statusleiste an, der Sie verwenden können, um Informationen anzuzeigen. Viele Anwendungen werden z. B. den Status der FESTSTELLTASTE, NUM-Taste und andere Schlüssel in der äußersten rechten Bereiche angezeigt. Anwendungen anzeigen häufig informativen Text in der am weitesten links stehende Fensterbereich (0), bezeichnet der "" Nachrichtenbereich. Beispielsweise verwendet die Standard-MFC-Statusleiste Nachrichtenbereich eine Zeichenfolge, die erläutern, der aktuell ausgewählte Element oder auf der Symbolleiste Menüschaltfläche angezeigt. Die Abbildung im [Statusleisten](../mfc/status-bar-implementation-in-mfc.md) zeigt eine Statusleiste aus einer-Anwendungs-Assistent erstellte MFC_Anwendung.  
  
 MFC wird standardmäßig nicht aktiviert einen `CStatusBar` Bereich, wenn es sich um den Bereich erstellt. Um einen Bereich zu aktivieren, müssen Sie verwenden die `ON_UPDATE_COMMAND_UI` -Makro für jeden Bereich auf den Status Leiste, und aktualisieren Sie die Bereiche. Da die Bereiche nicht versendet **WM_COMMAND** Nachrichten (sie sind nicht wie Symbolleisten-Schaltflächen), müssen Sie den Code manuell eingeben.  
  
 Nehmen wir beispielsweise an, die einen Bereich verfügt über `ID_INDICATOR_PAGE` sowie die Befehls-ID, die sie die aktuelle Seitenzahl in einem Dokument enthält. Das folgende Verfahren beschreibt, wie einen neuen Bereich in der Statusleiste zu erstellen.  
  
### <a name="to-make-a-new-pane"></a>Um einen neuen Bereich zu machen.  
  
1.  Definieren des Bereichs Befehls-ID.  
  
     Auf der **Ansicht** Menü klicken Sie auf **Ressourcenansicht**. Mit der rechten Maustaste in den Ressourcen-Projekt, und klicken Sie auf **Ressourcensymbole**. Klicken Sie im Dialogfeld "Ressourcensymbole" auf `New`. Geben Sie einen Namen der Befehls-ID: z. B. `ID_INDICATOR_PAGE`. Geben Sie einen Wert für die ID, oder übernehmen Sie den Wert im Dialogfeld "Ressourcensymbole" vorgeschlagen. Z. B. für `ID_INDICATOR_PAGE`, akzeptieren Sie den Standardwert. Schließen Sie das Dialogfeld "Ressourcensymbole".  
  
2.  Definieren Sie eine Standardzeichenfolge, die im Bereich anzuzeigen.  
  
     Ressourcenansicht öffnen, doppelklicken Sie auf **Zeichenfolgentabelle** im Fenster, das für Ihre Anwendung Ressourcentypen aufgelistet. Mit der **Zeichenfolgentabelle** Editor geöffnet ist, wählen Sie **neue Zeichenfolge** aus der **einfügen** Menü. Wählen Sie im Fenster Eigenschaften die Befehls-ID des Bereichs (z. B. `ID_INDICATOR_PAGE`), und geben Sie einen Standardwert, z. B. "Seite". Die Zeichenfolgen-Editor zu schließen. (Sie benötigen eine Standardzeichenfolge, die einen Compilerfehler zu vermeiden.)  
  
3.  Fügen Sie den Bereich, um die **Indikatoren** Array.  
  
     In der Datei MAINFRM. CPP, suchen Sie die **Indikatoren** Array. Dieses Array enthält die Befehls-IDs für alle Indikatoren für die Statusleiste, in der Reihenfolge von links nach rechts. Geben Sie an der entsprechenden Stelle im Array, die Befehls-ID des Bereichs, wie hier gezeigt für `ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 Die empfohlene Vorgehensweise zum Anzeigen von Text in einem Bereich besteht im Aufrufen der **SetText** Memberfunktion der Klasse `CCmdUI` in einer Update-Handler-Funktion für den Bereich. Möglicherweise möchten z. B. eine ganzzahlige Variable einrichten `m_nPage` , enthält die aktuelle Seitenzahl und die Verwendung **SetText** für eine Zeichenfolgenversion dieser Zahl im Bereich Text festzulegen.  
  
> [!NOTE]
>  Die **SetText** Ansatz wird empfohlen. Es ist möglich, diese Aufgabe mit etwas geringerer durch Aufrufen der `CStatusBar` Memberfunktion `SetPaneText`. Deshalb benötigen Sie dennoch einen updatehandler. Ohne solchen einen Handler für den Bereich deaktiviert MFC automatisch Bereich sein Inhalt gelöscht.  
  
 Das folgende Verfahren zeigt, wie eine Update-Handler-Funktion, die zum Anzeigen von Text in einem Bereich verwendet wird.  
  
#### <a name="to-make-a-pane-display-text"></a>Um ein Fenster Text angezeigt  
  
1.  Fügen Sie einen Update-Befehlshandler für den Befehl.  
  
     Einen Prototyp für den Handler manuell hinzufügen, wie hier gezeigt für `ID_INDICATOR_PAGE` (in MAINFRM. H):  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  In der entsprechenden. CPP-Datei, fügen Sie den Handler-Definition hinzu, wie hier gezeigt für `ID_INDICATOR_PAGE` (in MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     Die letzten drei Zeilen der diesen Handler werden der Code, der den Text anzeigt.  
  
3.  Fügen Sie in die entsprechende meldungszuordnung, die `ON_UPDATE_COMMAND_UI` -Makro, wie hier gezeigt für `ID_INDICATOR_PAGE` (in MAINFRM. CPP):  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 Nachdem Sie den Wert definieren die `m_nPage` Membervariable (Klasse `CMainFrame`), dieses Verfahren führt dazu, dass die Seitenzahl im Bereich während der Verarbeitung im Leerlauf auf die gleiche Weise angezeigt werden, dass die Anwendung andere Indikatoren aktualisiert. Wenn `m_nPage` Änderungen, die anzeigeänderungen, während der nächsten Leerlaufschleife.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Aktualisieren von Benutzeroberflächenobjekten (Gewusst wie: Aktualisieren von Symbolleisten-Schaltflächen und Menüelementen als Programm netzwerkbedingungen ändern)](../mfc/how-to-update-user-interface-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der Statusleiste in MFC](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar-Klasse](../mfc/reference/cstatusbar-class.md)
