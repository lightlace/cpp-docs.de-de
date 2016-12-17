---
title: "Handler f&#252;r Meldungszuordnungsbereiche"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsbehandlung, Befehlsupdatehandler"
  - "Befehls-IDs, Meldungszuordnungen"
  - "Befehlsrouting, Befehlsupdatehandler"
  - "Befehlsupdatehandler"
  - "Steuerelemente-Benachrichtigungsmeldungen"
  - "Steuerelemente [MFC], Benachrichtigungen"
  - "Handlerfunktionen"
  - "Handlerfunktionen, Deklarieren"
  - "Handlerfunktionen, Meldungszuordnungsbereiche"
  - "Handler"
  - "Handler, Meldungszuordnungsbereiche"
  - "Zuordnungen, Meldungsbereiche"
  - "Meldungshandler"
  - "Meldungsbehandlung, Meldungshandlerfunktionen"
  - "Meldungszuordnungen, Meldungshandlerfunktionen"
  - "Meldungszuordnungen, Bereiche"
  - "Meldungsbereiche"
  - "Meldungsbereiche, Zuordnen"
  - "Meldungszuordnungsbereiche"
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Handler f&#252;r Meldungszuordnungsbereiche
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie ein Bereich von Meldungen zu einer einzelnen Meldungshandlerfunktion zuordnet \(anstelle der Meldung der Zuordnung eine nur eine Funktion\).  
  
 Manchmal, als Sie mehr als eine Meldung oder Steuerelementbenachrichtigung genauso genau verarbeiten müssen.  So einen Situationen möchten Sie möglicherweise alle Nachrichten zu einer einzelnen Handlerfunktion zuordnen.  Meldungszuordnungsbereiche ermöglichen, um dies für einen zusammenhängenden Bereich von Meldungen zu tun:  
  
-   Sie können Bereiche von Befehls\-IDs zuordnen:  
  
    -   Eine Befehlshandlerfunktion.  
  
    -   Eine Befehlsaktualisierungshandlerfunktion.  
  
-   Steuerelement\-Benachrichtigungen Sie können für einen Bereich von Steuerelement\-IDs zu einer Meldungshandlerfunktion zuordnen.  
  
 Themen beschrieben in diesem Artikeleinschließung:  
  
-   [Schreiben des Meldungszuordnungseintrags](#_core_writing_the_message.2d.map_entry)  
  
-   [Deklarieren der Handlerfunktion](#_core_declaring_the_handler_function)  
  
-   [Beispiel für einen Bereich von Befehls\-IDs](#_core_example_for_a_range_of_command_ids)  
  
-   [Beispiel für einen Bereich von Steuerelement\-IDs](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> Schreiben des Meldungszuordnungseintrags  
 in der CPP\-Datei fügen Sie den Eintrag in der Meldungszuordnung, wie im folgenden Beispiel gezeigt:  
  
 [!CODE [NVC_MFCMessageHandling#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#6)]  
  
 Der Eintrag in der Meldungszuordnung umfasst folgende Elemente:  
  
-   Das Meldungszuordnungsbereichsmakro:  
  
    -   [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)  
  
    -   [ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)  
  
    -   [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)  
  
-   Parameter dem Makro:  
  
     Die ersten beiden Makros verwenden drei Parameter:  
  
    -   Die Befehls\-ID, die den Bereich beginnt  
  
    -   Die Befehls\-ID, die den Bereich beendet  
  
    -   Der Name der Meldungshandlerfunktion  
  
     Der Bereich von Befehls\-IDs müssen zusammenhängend sein.  
  
     Das dritte Makro, `ON_CONTROL_RANGE`, verwendet einen zusätzlichen ersten Parameter: eine Steuerelement\-Benachrichtigung, wie **EN\_CHANGE**.  
  
##  <a name="_core_declaring_the_handler_function"></a> Deklarieren der Handlerfunktion  
 Fügen Sie der Handlerfunktionsdeklaration in hinzu. Headerdatei.  Der folgende Code zeigt, wie dieser potenziell aussehen, wie unten an:  
  
 [!CODE [NVC_MFCMessageHandling#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#7)]  
  
 Handlerfunktionen einzige für Befehle verwenden normalerweise keine Parameter.  Mit Ausnahme von Aktualisierungshandlerfunktionen Handlerfunktionen benötigen für Meldungszuordnungsbereiche einen zusätzlichen Parameter, `nID`, des Typs **UINT**.  Dieser Parameter ist der erste Parameter.  Der zusätzliche Parameter bündelt die zusätzliche Befehls\-ID unter, die erforderlich ist, um anzugeben, die der Benutzer ausgewählt hat tatsächlich Befehl verwenden.  
  
 Weitere Informationen über Parameteranforderungen zum Aktualisieren der Handlerfunktionen, finden Sie unter [Beispiel für einen Bereich von Befehls\-IDs](#_core_example_for_a_range_of_command_ids).  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> Beispiel für einen Bereich von Befehls\-IDs  
 Als können Bereiche?  Ein Beispiel ist in den Behandlungsbefehlen wie dem Zoombefehl im MFC\-Beispiel [HIERSVR](../top/visual-cpp-samples.md).  Dieser Befehl vergrößert die Ansicht und skaliert es zwischen 25% und 300% seiner normalen Größe.  Ansichtsklasse HIERSVRS verwendet einen Bereich, um die Zoombefehle mit einem Eintrag in der Meldungszuordnung zu behandeln, der diesem ähnelt:  
  
 [!CODE [NVC_MFCMessageHandling#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#8)]  
  
 Wenn Sie den Eintrag in der Meldungszuordnung schreiben, geben Sie an:  
  
-   Zwei Befehls\-IDs, Anfang und Ende ein zusammenhängender Bereich.  
  
     Hier sind sie `ID_VIEW_ZOOM25` und `ID_VIEW_ZOOM300`.  
  
-   Der Name der Handlerfunktion für die Befehle.  
  
     Hier ist es `OnZoom`.  
  
 Die Funktionsdeklaration würde diesem ähneln:  
  
 [!CODE [NVC_MFCMessageHandling#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#9)]  
  
 Der Fall von Aktualisierungshandlerfunktionen ist ähnlich, und wahrscheinlich, hilfreich breit.  Es ist recht üblich, `ON_UPDATE_COMMAND_UI`\-Handler für einige Befehle zu schreiben und zu suchen Schreiben, oder Kopieren, codieren derselbe immer wieder.  Die Lösung besteht darin, einen Bereich von Befehls\-IDs zu einer Aktualisierungshandlerfunktion mithilfe des Makros `ON_UPDATE_COMMAND_UI_RANGE` zuzuordnen.  Die Befehls\-IDs müssen einen zusammenhängenden Bereich besteht.  Ein Beispiel finden Sie den **OnUpdateZoom**\-Handler und den `ON_UPDATE_COMMAND_UI_RANGE` \- Eintrag in der Meldungszuordnung in der Ansichtsklasse des HIERSVR\-Beispiel.  
  
 Aktualisierungshandlerfunktionen einzige für Befehle verwenden normalerweise einen einzelnen Parameter, `pCmdUI`, des Typs **CCmdUI\***.  Im Gegensatz Handlerfunktionen benötigen Aktualisierungshandlerfunktionen für Meldungszuordnungsbereiche keinen zusätzlichen Parameter, `nID`, des Typs **UINT**.  Die Befehls\-ID, die erforderlich ist, um anzugeben, die den Benutzer ausgewählten Befehl tatsächlich, wird im `CCmdUI`\-Objekt gefunden.  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> Beispiel für einen Bereich von Steuerelement\-IDs  
 Ein weiterer interessanter Fall ordnet Steuerelement\-Benachrichtigungen für einen Bereich von Steuerelement\-IDs einem einzelnen Handler an.  Angenommen, der Benutzer eines der auf 10 Schaltflächen klicken kann.  Um alle 10 Schaltflächen auf einem Handler zuzuordnen, wird der Eintrag in der Meldungszuordnung wie folgt aussehen:  
  
 [!CODE [NVC_MFCMessageHandling#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#10)]  
  
 Wenn Sie das `ON_CONTROL_RANGE`\-Makro in der Meldungszuordnung schreiben, geben Sie an:  
  
-   Eine bestimmte Steuerelement\-Benachrichtigung.  
  
     Hier ist es **BN\_CLICKED**.  
  
-   Die Steuerelement\-ID\-Werte dem zusammenhängenden Bereich von Steuerelementen.  
  
     Hier sind diese `IDC_BUTTON1` und `IDC_BUTTON10`.  
  
-   Der Name der Meldungshandlerfunktion.  
  
     Hier ist es `OnButtonClicked`.  
  
 Wenn Sie die Handlerfunktion schreiben, den **UINT** zusätzlichen Parameter, wie im Folgenden dargestellt:  
  
 [!CODE [NVC_MFCMessageHandling#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#11)]  
  
 Der Handler für `OnButtonClicked` eine einzelne **BN\_CLICKED** Meldung akzeptiert keine Parameter.  Derselbe Handler für einen Bereich von Schaltflächen wird ein **UINT**.  Der zusätzliche Parameter können Identifizieren des jeweiligen Steuerelements zu, das zum Generieren der **BN\_CLICKED** Meldung zuständig ist.  
  
 Der Code, der im Beispiel gezeigt wird, ist typisch: den Wert konvertieren, an `int` innerhalb des Meldungsbereiches und \-behauptung, dass dieses der Fall ist.  Anschließend ergriffen Sie möglicherweise etwas unterschiedliche Aktionen, je nachdem auf die Schaltfläche geklickt wurde.  
  
## Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)