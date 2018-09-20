---
title: Wie das Framework Meldungszuordnungen durchsucht | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message maps [MFC], searching
ms.assetid: fd1df878-5601-45d7-bd1f-b8f8e65b9a17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02d111cfdd4db1d3ce586d65ebbef84fd488fba6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436168"
---
# <a name="how-the-framework-searches-message-maps"></a>Wie das Framework Meldungszuordnungen durchsucht

Das Framework durchsucht die meldungszuordnung Tabelle nach Übereinstimmungen mit eingehenden Nachrichten. Sobald Sie eine Meldungszuordnungseintrags für jede Nachricht, dass eine Klasse behandeln und die entsprechenden Handler schreiben soll schreiben, ruft das Framework automatisch die Handler an. Die folgenden Themen erläutern die meldungszuordnung Suche:

- [Wo sich meldungszuordnungen befinden](../mfc/where-to-find-message-maps.md)

- [Abgeleitete meldungszuordnungen](../mfc/derived-message-maps.md)

- [Bereiche von Nachrichten, Befehls-IDs oder Steuerelement-IDs zuordnen auf einen handler](../mfc/handlers-for-message-map-ranges.md)

## <a name="see-also"></a>Siehe auch

[Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

