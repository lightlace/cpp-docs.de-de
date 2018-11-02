---
title: Wo sich Meldungszuordnungen befinden
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: ab21369cecfa977a8397e7e2a7e68394e86e6927
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533470"
---
# <a name="where-to-find-message-maps"></a>Wo sich Meldungszuordnungen befinden

Wenn Sie eine neue Skelette-Anwendung mit der Anwendungs-Assistenten erstellen, schreibt der Anwendungs-Assistent eine meldungszuordnung für jede Befehlsziel Klasse, die sie erstellt für Sie. Dies schließt Ihre abgeleiteten Anwendung, Dokument, Ansicht und Rahmenfensterklassen. Einige diese meldungszuordnungen verfügen bereits über die Einträge, die vom Anwendungs-Assistenten für bestimmte Nachrichten und die vordefinierten Befehle bereitgestellt, und einige sind nur Platzhalter für Handler, die Sie hinzufügen möchten.

Meldungszuordnung für eine Klasse befindet sich in der. CPP-Datei für die Klasse. Arbeiten mit den grundlegenden meldungszuordnungen, die die Anwendungs-Assistent erstellt, verwenden Sie das Fenster "Eigenschaften", fügen Sie Einträge für die Meldungen und Befehle, die jede Klasse behandelt. Eine typische Nachricht, die Zuordnung kann wie folgt aussehen, nachdem Sie einige Einträge hinzugefügt:

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

Die meldungszuordnung besteht aus einer Auflistung von Makros. Zwei Makros [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) und [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), Zuordnen von Klammern die meldungszuordnung. Andere Makros, wie z. B. `ON_COMMAND`, geben Sie in der meldungszuordnung Inhalt.

> [!NOTE]
>  Die Meldungszuordnungsmakros sind nicht durch ein Semikolon folgen.

Wenn Sie den Assistenten zum Hinzufügen von Klassen verwenden, um eine neue Klasse zu erstellen, wird eine meldungszuordnung für die Klasse angegeben. Alternativ können Sie eine meldungszuordnung, die manuell mit dem Quellcode-Editor erstellen.

## <a name="see-also"></a>Siehe auch

[So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

