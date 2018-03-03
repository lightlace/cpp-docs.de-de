---
title: "Handler für Meldungszuordnungsbereiche | Microsoft Docs"
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
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b44288d21ab2df68468b0e39cb1ee35b7b8810
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-message-map-ranges"></a>Handler für Meldungszuordnungsbereiche
In diesem Artikel wird erläutert, wie einen Bereich von Nachrichten an eine einzelne Nachricht Handler-Funktion (und nicht nur eine bestimmte Funktion eine Nachricht zuordnen) zugeordnet werden.  
  
 Es gibt Situationen, wenn mehr als eine Nachricht oder Control-Benachrichtigung auf genau die gleiche Weise verarbeitet werden muss. Möglicherweise möchten Sie alle Nachrichten an einen einzelnen Handlerfunktion zuordnen, solche Zeiten. Meldungszuordnungsbereiche können Sie hierzu für einen zusammenhängenden Bereich von Nachrichten:  
  
-   Sie können Bereiche der Befehls-IDs zuzuordnen:  
  
    -   Ein Befehl Handler-Funktion.  
  
    -   Die Handlerfunktion ein Befehl Update.  
  
-   Sie können eine Meldungshandlerfunktion Steuerelemente-benachrichtigungsmeldungen für einen Bereich von Steuerelement-IDs zuordnen.  
  
 In diesem Artikel behandelten Themen werden behandelt:  
  
-   [Schreiben die Meldungszuordnungseintrags](#_core_writing_the_message.2d.map_entry)  
  
-   [Deklarieren die Handlerfunktion](#_core_declaring_the_handler_function)  
  
-   [Beispiel für einen Bereich der Befehls-IDs](#_core_example_for_a_range_of_command_ids)  
  
-   [Beispiel für einen Bereich von Steuerelement-IDs](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a>Schreiben Sie die Meldungszuordnungseintrags  
 In der. CPP-Datei, die Ihre Meldungszuordnungseintrags hinzufügen, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]  
  
 Die Meldungszuordnungseintrags besteht aus den folgenden Elementen:  
  
-   Das meldungszuordnung Range-Makro:  
  
    -   [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)  
  
    -   [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)  
  
    -   [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)  
  
-   Parameter für das Makro:  
  
     Die ersten zwei Makros werden drei Parameter annehmen:  
  
    -   Die Befehls-ID, die der Bereich beginnt  
  
    -   Die Befehls-ID, die der Bereich endet  
  
    -   Der Name der Meldungshandlerfunktion  
  
     Der Bereich der Befehls-IDs muss zusammenhängend sein.  
  
     Das dritte Makro `ON_CONTROL_RANGE`, akzeptiert einen weiteren ersten Parameter: eine Steuerelement-Benachrichtigung angezeigt, wie z. B. **EN_CHANGE**.  
  
##  <a name="_core_declaring_the_handler_function"></a>Deklarieren Sie die Handlerfunktion  
 Fügen Sie die Funktionsdeklaration Handler in der. H-Datei. Der folgende Code zeigt, wie dies aussehen könnte, wie unten dargestellt:  
  
 [!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]  
  
 Handlerfunktionen für einzelne Befehle nehmen normalerweise keine Parameter an. Mit Ausnahme von Update Handlerfunktionen, Handlerfunktionen für Meldungszuordnungsbereiche erfordern einen zusätzlichen Parameter `nID`, des Typs **"uint"**. Dieser Parameter ist der erste Parameter. Die zusätzliche Parameter verfügt, die zusätzliche Befehls-ID, welcher Befehl anzugeben, der Benutzer tatsächlich ausgewählt haben.  
  
 Weitere Informationen zu den parameteranforderungen für die Aktualisierung von Handlerfunktionen finden Sie unter [Beispiel für einen Bereich der Befehls-IDs](#_core_example_for_a_range_of_command_ids).  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a>Beispiel für einen Bereich von Befehls-IDs  
 Wenn können Sie Bereiche, die ein Beispiel ist bei der Verarbeitung von Befehlen, wie mit dem Befehl "Zoom" in der MFC-Beispiel [HIERSVR](../visual-cpp-samples.md). Mit diesem Befehl wird die Ansicht zwischen 25 % und 300 % Normalgröße skalieren Zeitsegments vergrößert. HIERSVR des View-Klasse verwendet einen Bereich, um den Zoom-Befehle mit einem Meldungszuordnungseintrags ähnelt dies behandeln:  
  
 [!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]  
  
 Wenn Sie die Meldungszuordnungseintrags schreiben, geben Sie folgende Schritte ausführen:  
  
-   Zwei Befehls-IDs, öffnend und schließend einen zusammenhängenden Bereich.  
  
     Hier werden `ID_VIEW_ZOOM25` und `ID_VIEW_ZOOM300`.  
  
-   Der Name der Handlerfunktion für Befehle.  
  
     Hier kann `OnZoom`.  
  
 Die Funktionsdeklaration würde diesem ähneln:  
  
 [!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]  
  
 Im Fall von Update Handlerfunktionen ist ähnlich und wahrscheinlich breitere hilfreich sein. Es ist üblich, das zum Schreiben `ON_UPDATE_COMMAND_UI` Handler für eine Reihe von Befehlen und selbst schreiben oder kopieren, den gleichen Code immer wieder zu finden. Die Lösung besteht darin, ordnen Sie einen Bereich von Befehls-IDs auf einen aktualisieren Handler-Funktion verwendet die `ON_UPDATE_COMMAND_UI_RANGE` Makro. Die Befehls-IDs müssen einen zusammenhängenden Bereich bilden. Ein Beispiel finden Sie die **OnUpdateZoom** Handler und die zugehörige `ON_UPDATE_COMMAND_UI_RANGE` Meldungszuordnungseintrags in Ansichtsklasse HIERSVR-Beispiel.  
  
 Aktualisieren von Handlerfunktionen für die einzelnen Befehle normalerweise einen einzelnen Parameter verwenden `pCmdUI`, des Typs **CCmdUI\***. Im Gegensatz zu Handlerfunktionen, Update Handlerfunktionen für Meldungszuordnungsbereiche erfordern keine zusätzlichen Parameter `nID`, des Typs **"uint"**. Die Befehls-ID, die benötigt wird, um anzugeben, mit welchem Befehl der Benutzer tatsächlich ausgewählt haben, befindet sich der `CCmdUI` Objekt.  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a>Beispiel für einen Bereich von Steuerelement-IDs  
 Eine andere interessanter Fall Zuordnen der Steuerelemente-benachrichtigungsmeldungen für einen Bereich von Steuerelement-IDs an einen einzigen Handler. Nehmen Sie an, dass der Benutzer eine 10 Schaltflächen klicken kann. Um alle 10 Schaltflächen zu einem Handler zuzuordnen, Ihre Meldungszuordnungseintrags sieht dann folgendermaßen aus:  
  
 [!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]  
  
 Beim Schreiben der `ON_CONTROL_RANGE` Makro in Ihrer nachrichtenzuordnung, die Sie angeben:  
  
-   Ein bestimmtes Steuerelement-Benachrichtigung.  
  
     Hier kann **BN_CLICKED**.  
  
-   Die Steuerelement-ID-Werte der zusammenhängenden Bereich von Steuerelementen zugeordnet.  
  
     Hier werden diese `IDC_BUTTON1` und `IDC_BUTTON10`.  
  
-   Der Name der Meldungshandlerfunktion.  
  
     Hier kann `OnButtonClicked`.  
  
 Wenn Sie die Handlerfunktion schreiben, geben Sie die zusätzlichen **"uint"** Parameter, wie im folgenden gezeigt:  
  
 [!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]  
  
 Die `OnButtonClicked` Handler für ein einzelnes **BN_CLICKED** Nachricht nimmt keine Parameter. Für einen Bereich von Schaltflächen mit der gleiche Handler nimmt eine **"uint"**. Ermöglicht der zusätzliche Parameter identifiziert das jeweilige Steuerelement verantwortlich für das Generieren der **BN_CLICKED** Nachricht.  
  
 Der Code im Beispiel gezeigt ist typisch: Konvertieren von der an übergebene Wert ein `int` innerhalb des Bereichs der Nachricht und die Bestätigung, dass dies der Fall ist. Sie können dann eine andere Aktion ausführen, je nachdem, die welche Schaltfläche geklickt wurde.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
