---
title: Wo sich Meldungszuordnungen befinden | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81958eda508a3e0b4b93ac0d169f3aa3bfece2a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434270"
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

