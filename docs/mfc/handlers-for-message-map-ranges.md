---
title: Handler für Meldungszuordnungsbereiche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 738d441cf88b41740cb0cff933916489cac683f2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073096"
---
# <a name="handlers-for-message-map-ranges"></a>Handler für Meldungszuordnungsbereiche

In diesem Artikel wird erläutert, wie Sie einen Bereich von Nachrichten an eine einzelne Nachricht Handler-Funktion (anstelle der Zuordnung eine Nachricht an nur eine Funktion) zuordnen.

Es gibt Situationen, wenn mehr als eine Nachricht oder die Control-Benachrichtigung auf genau die gleiche Weise verarbeitet werden muss. Zu solchen Zeitpunkten möglicherweise möchten Sie alle Nachrichten an eine Funktion der einzelnen Handler zugeordnet. Meldungszuordnungsbereiche können Sie dies für einen zusammenhängenden Bereich von Nachrichten durchführen:

- Sie können Bereiche der Befehls-IDs zuordnen:

   - Eine Befehls-Handler-Funktion.

   - Eine Handlerfunktion für den Befehl Update.

- Sie können Steuerelemente-benachrichtigungsmeldungen für einen Bereich von Steuerelement-IDs eine Handlerfunktion Nachricht zuordnen.

In diesem Artikel behandelten Themen umfassen:

- [Schreiben die Meldungszuordnungseintrags](#_core_writing_the_message.2d.map_entry)

- [Deklarieren die Handler-Funktion](#_core_declaring_the_handler_function)

- [Beispiel für einen Bereich für Befehls-IDs](#_core_example_for_a_range_of_command_ids)

- [Beispiel für einen Bereich von Steuerelement-IDs](#_core_example_for_a_range_of_control_ids)

##  <a name="_core_writing_the_message.2d.map_entry"></a> Schreiben Sie die Meldungszuordnungseintrags

In der. CPP-Datei, fügen Sie Ihrem Meldungszuordnungseintrags hinzu, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

Die Meldungszuordnungseintrags besteht aus den folgenden Elementen:

- Die meldungszuordnung Range-Makro:

   - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

   - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

   - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- Die Parameter in das Makro:

   Die ersten zwei Makros werden drei Parameter:

   - Die Befehls-ID, die der Bereich beginnt

   - Die Befehls-ID, die der Bereich endet

   - Der Name der Handlerfunktion Nachricht

   Der Bereich der Befehls-IDs muss zusammenhängend sein.

   Das dritte Makro, `ON_CONTROL_RANGE`, einen zusätzlichen Parameter für die erste benötigt: eine Steuerelement-benachrichtigungsmeldung, wie etwa **EN_CHANGE-Ereignis**.

##  <a name="_core_declaring_the_handler_function"></a> Deklarieren Sie die Handler-Funktion

Fügen Sie die Handler-Funktionsdeklaration in der. H-Datei. Der folgende Code zeigt, wie dies aussehen könnte, wie unten dargestellt:

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

Handlerfunktionen für die einzelnen Befehle akzeptieren keine Parameter in der Regel. Mit Ausnahme der Update-Handlerfunktionen, erfordern Handlerfunktionen für Meldungszuordnungsbereiche einen zusätzlichen Parameter, *nID*, des Typs **UINT**. Dieser Parameter ist der erste Parameter. Der zusätzliche Parameter verfügt, die zusätzliche Befehls-ID, die erforderlich sind, an welcher Befehl, der Benutzer tatsächlich ausgewählt haben.

Weitere Informationen zu den parameteranforderungen für die Aktualisierung Handlerfunktionen finden Sie unter [Beispiel für einen Bereich der Befehls-IDs](#_core_example_for_a_range_of_command_ids).

##  <a name="_core_example_for_a_range_of_command_ids"></a> Beispiel für einen Bereich von Befehls-IDs

Wenn können Sie Bereiche, die ein Beispiel ist bei der Verarbeitung von Befehlen wie der Zoom-Befehl in der MFC-Beispiel [HIERSVR](../visual-cpp-samples.md). Mit diesem Befehl wird die Ansicht zwischen 25 und 300 % seiner normalen Größe skalieren vergrößert. HIERSVR des View-Klasse verwendet einen Bereich, um die Zoom-Befehle mit einer Meldungszuordnungseintrags ähnlich wie dieses zu verarbeiten:

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

Wenn Sie die Meldungszuordnungseintrags schreiben, geben Sie folgende Schritte ausführen:

- Zwei Befehls-IDs beginnen und enden einen zusammenhängenden Bereich.

   Nachfolgend finden sie **ID_VIEW_ZOOM25** und **ID_VIEW_ZOOM300**.

- Der Name der Handlerfunktion für die Befehle.

   Hier hat `OnZoom`.

Die Funktionsdeklaration würde so aussehen:

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

Im Fall von Update-Handlerfunktionen ist ähnlich und wahrscheinlich mit der zunehmenden Verbreitung nützlich sein. Es ist üblich, schreiben `ON_UPDATE_COMMAND_UI` Handler für eine Reihe von Befehlen, und schreiben oder kopieren, den gleichen Code immer wieder. Die Lösung besteht darin, ordnen einen Bereich des Befehls-IDs auf einen aktualisieren Handler-Funktion verwendet die `ON_UPDATE_COMMAND_UI_RANGE` Makro. Die Befehls-IDs müssen es sich um einen zusammenhängenden Bereich bilden. Ein Beispiel finden Sie unter den `OnUpdateZoom` Handler und die zugehörige `ON_UPDATE_COMMAND_UI_RANGE` Meldungszuordnungseintrags in der beispielanwendung HIERSVR Ansichtsklasse.

Handlerfunktionen aktualisieren, für die einzelnen Befehle normalerweise einen einzelnen Parameter, dauern *nämlich pCmdUI*, des Typs `CCmdUI*`. Im Gegensatz zu Handlerfunktionen, Aktualisierungsfunktionen der Handler für Meldungszuordnungsbereiche erfordern keine zusätzlichen Parameter *nID*, des Typs **UINT**. Die Befehls-ID, die benötigt wird, um anzugeben, welchen Befehl der Benutzer tatsächlich ausgewählt haben, befindet sich der `CCmdUI` Objekt.

##  <a name="_core_example_for_a_range_of_control_ids"></a> Beispiel für einen Bereich von Steuerelement-IDs

Ein weiterer interessanter Fall ist einem einzelnen Handler Steuerelemente-benachrichtigungsmeldungen für einen Bereich von Steuerelement-IDs zugeordnet. Nehmen wir an, dass der Benutzer eine der 10 Schaltflächen klicken kann. Um einen Handler für alle 10 Schaltflächen zuzuordnen, würde Ihre Meldungszuordnungseintrags wie folgt aussehen:

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

Beim Schreiben der `ON_CONTROL_RANGE` Makro in der meldungszuordnung, die Sie angeben:

- Einem bestimmten Steuerelement-Benachrichtigung.

   Hier hat **BN_CLICKED**.

- Die Steuerelement-ID-Werte der zusammenhängenden Bereich von Steuerelementen zugeordnet.

   Hier sind diese **IDC_BUTTON1** und **IDC_BUTTON10**.

- Der Name der Handlerfunktion Nachricht.

   Hier hat `OnButtonClicked`.

Wenn Sie die Handler-Funktion schreiben, geben Sie die zusätzlichen **UINT** Parameter, wie im folgenden gezeigt:

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

Die `OnButtonClicked` Handler für ein einzelnes **BN_CLICKED** Nachricht nimmt keine Parameter. Für eine Reihe von Schaltflächen der gleiche Handler nimmt eine **UINT**. Ermöglicht der zusätzliche Parameter identifiziert das jeweilige Steuerelement erzeugt die **BN_CLICKED** Nachricht.

Der Code im Beispiel gezeigt ist typisch: Konvertieren des Werts, die an eine `int` innerhalb des Bereichs der Nachricht und bestätigt, dass dies der Fall ist. Anschließend können Sie eine andere Aktion ausgeführt, je nachdem, die welche Schaltfläche geklickt wurde.

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
