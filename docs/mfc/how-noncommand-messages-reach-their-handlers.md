---
title: Wie nicht befehlsbasierte Meldungen ihre Handler erreichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5c38a1d4294993170cfeff64be6a83700fa7497
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373437"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Wie nicht befehlsbasierte Meldungen ihre Handler erreichen

Im Gegensatz zu den Befehlen standard-Windows-Nachrichten werden nicht durch eine Kette von Befehlsziele weitergeleitet, aber erfolgt in der Regel durch das Fenster, die an den Windows die Nachricht sendet. Das Fenster möglicherweise ein Hauptrahmenfenster, eines untergeordneten MDI-Fensters, ein Standardsteuerelement, ein Dialogfeld, eine Sicht oder eine andere Art von untergeordneten Fensters.

Bei der Ausführung jedes Windows-Fenster an ein Window-Objekt angefügt ist (direkt oder indirekt von abgeleiteten `CWnd`), die eigene Funktionen zugeordnete Meldung, Zuordnung und der Handler hat. Das Framework verwendet die meldungszuordnung – wie für einen Befehl, eingehende Nachrichten an die Handler zugeordnet.

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

