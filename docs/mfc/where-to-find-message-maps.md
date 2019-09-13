---
title: Wo sich Meldungszuordnungen befinden
ms.date: 11/04/2016
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
ms.openlocfilehash: c50c6fc1134f579859530972dc864103c4e0ebcf
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907356"
---
# <a name="where-to-find-message-maps"></a>Wo sich Meldungszuordnungen befinden

Wenn Sie mit dem Anwendungs-Assistenten eine neue Skeleton-Anwendung erstellen, schreibt der Anwendungs-Assistent eine Meldungs Zuordnung für jede Befehls Zielklasse, die für Sie erstellt wird. Dies schließt die abgeleiteten Anwendungs-, Dokument-, Ansichts-und Rahmen Fenster Klassen ein. Einige dieser Nachrichten Zuordnungen verfügen bereits über die Einträge, die vom Anwendungs-Assistenten für bestimmte Nachrichten und vordefinierte Befehle bereitgestellt werden, und einige sind nur Platzhalter für Handler, die Sie hinzufügen.

Die Meldungs Zuordnung einer Klasse befindet sich im. Cpp-Datei für die-Klasse. Wenn Sie mit den grundlegenden Meldungs Zuordnungen arbeiten, die der Anwendungs-Assistent erstellt, verwenden Sie den [Klassen-Assistenten](reference/mfc-class-wizard.md) , um Einträge für die Nachrichten und Befehle hinzuzufügen, die von den einzelnen Eine typische Meldungs Zuordnung könnte wie folgt aussehen, nachdem Sie einige Einträge hinzugefügt haben:

[!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]

Die Meldungs Zuordnung besteht aus einer Auflistung von Makros. Zwei Makros, [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) und [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), Klammern die Meldungs Zuordnung. Andere Makros, wie z `ON_COMMAND`. b., füllen den Inhalt der Nachrichten Zuordnung aus.

> [!NOTE]
>  Auf die Nachrichten Zuordnungs Makros folgt kein Semikolon.

Wenn Sie mit dem Assistenten zum Hinzufügen von Klassen eine neue Klasse erstellen, wird eine Meldungs Zuordnung für die-Klasse bereitstellt. Alternativ dazu können Sie eine Meldungs Zuordnung auch manuell mithilfe des Quell Code-Editors erstellen.

## <a name="see-also"></a>Siehe auch

[So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)
