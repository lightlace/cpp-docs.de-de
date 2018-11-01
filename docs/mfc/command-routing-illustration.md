---
title: Befehlsroutingerläuterung
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 3bc7c33762ab1868b29732d17e1a2e9700d11cf7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584560"
---
# <a name="command-routing-illustration"></a>Befehlsroutingerläuterung

Um zu veranschaulichen, betrachten Sie eine Nachricht über ein Menüelement in einer MDI-Anwendung-Menü "Bearbeiten" Alle löschen aus. Nehmen wir an, dass die Handler-Funktion für diesen Befehl erfolgt eine Memberfunktion der Anwendung Dokumentklasse sein. Hier ist, wie dieses Befehls den Handler erreicht, nachdem der Benutzer das Menüelement auswählt:

1. Das Hauptrahmenfenster empfängt die Nachricht zuerst an.

1. Der MDI-Hauptrahmenfenster gibt dem momentan aktiven untergeordnete MDI-Fenster eine Möglichkeit, den Befehl behandeln.

1. Das standardmäßige routing von einem untergeordneten MDI-Rahmenfenster kann der Ansicht an der Befehlszeile vor dem Überprüfen ihre eigene meldungszuordnung.

1. Die Ansicht ihre eigene meldungszuordnung zuerst überprüft und als Nächstes den Befehl leitet kein Handler auf, suchen, an dessen zugeordnete Dokument.

1. Das Dokument überprüft seine meldungszuordnung und sucht nach einem Handler. Dieses Dokument-Memberfunktion aufgerufen wird, und das routing wird beendet.

Wenn das Dokument keinen Handler hatte, würden sie als Nächstes den Befehl an seine Dokumentvorlage weiterleiten. Klicken Sie dann würde der Befehl, um die Ansicht, und klicken Sie dann das Rahmenfenster zurück. Das Rahmenfenster würde seine meldungszuordnung, aktivieren Sie zum Schluss. Wenn auch die Überprüfung fehlgeschlagen ist, würde der Befehl zurück an die Haupt-MDI-Rahmenfenster und dann auf das Anwendungsobjekt weitergeleitet werden, das endgültige Ziel nicht behandelten Befehle.

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

