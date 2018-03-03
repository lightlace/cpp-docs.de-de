---
title: Wo sich Meldungszuordnungen befinden | Microsoft Docs
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
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fa0b0b31d76c55851d69f4c528f11e7d23ff0d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-find-message-maps"></a>Wo sich Meldungszuordnungen befinden
Wenn Sie eine neue skelettanwendung mit dem Assistenten zum Erstellen, schreibt der Anwendungs-Assistent eine meldungszuordnung für jede Befehlsziel Klasse, die es erstellt für Sie. Dies schließt die abgeleiteten Anwendung, Dokument anzeigen und Rahmenfensterklassen. Einige dieser meldungszuordnungen wurde bereits die Einträge, die vom Anwendungs-Assistenten für bestimmte Nachrichten und die vordefinierten Befehle bereitgestellt, und einige sind einfach Platzhalter für Handler, die hinzugefügt wird.  
  
 Meldungszuordnung für eine Klasse befindet sich der. CPP-Datei für die Klasse. Arbeiten mit den grundlegenden meldungszuordnungen, die die Anwendungs-Assistent erstellt, verwenden Sie das Eigenschaftenfenster zum Hinzufügen von Einträgen für die Meldungen und Befehle, die jede Klasse behandelt. Nachdem Sie einige Einträge hinzufügen, könnte eine typische Nachricht, die Zuordnung wie folgt aussehen:  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 Die meldungszuordnung besteht aus einer Auflistung von Makros. Zwei Makros [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) und [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), Klammer die meldungszuordnung. Andere Makros, wie z. B. `ON_COMMAND`, füllen Sie die meldungszuordnung Inhalt.  
  
> [!NOTE]
>  Die Meldungszuordnungsmakros folgt sind nicht durch Semikolons getrennt ein.  
  
 Wenn Sie die Klasse hinzufügen-Assistenten verwenden, um eine neue Klasse zu erstellen, stellt er eine meldungszuordnung für die Klasse. Alternativ können Sie eine meldungszuordnung, die manuell mit dem Quellcode-Editors erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)

