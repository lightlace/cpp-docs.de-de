---
title: Wie das Framework Code aufruft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68db9107a8d2d113e9118c9cf125acb2798edcd4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373869"
---
# <a name="how-the-framework-calls-your-code"></a>Wie das Framework Code aufruft

Es ist entscheidend, um die Beziehung zwischen Quellcode und den Code in MFC-Framework zu verstehen. Wenn Ihre Anwendung ausgeführt wird, die meisten der ablaufsteuerung befindet sich in die Framework Code. Das Framework verwaltet die Nachrichtenschleife aus, die Nachrichten von Windows abruft, da der Benutzer Befehle auswählt, und Bearbeiten von Daten in einer Ansicht. Ereignisse, die das Framework selbst behandeln können verlassen überhaupt nicht auf Ihren Code. Das Framework beispielsweise weiß, wie Sie das Fenster zu schließen und beenden die Anwendung als Reaktion auf Benutzerbefehle. Wie sie diese Aufgaben behandelt, verwendet das Framework meldungshandlers und virtuelle C++-Funktionen erhalten Sie Gelegenheit, Antworten auf diese Ereignisse ebenfalls an. Ihr Code ist jedoch nicht im Steuerelement. Das Framework ist.

Das Framework ruft Ihren Code für die anwendungsspezifische Ereignisse. Z. B. wenn der Benutzer einen Befehl auswählt, das Framework leitet den Befehl auf eine Sequenz von C++-Objekte: das aktuelle Ansicht- und Frame-Fenster, das die Ansicht des Dokuments Dokumentvorlage und das-Objekt zugeordnete Dokument. Wenn eines dieser Objekte den Befehl behandeln kann, wird dies durchgeführt, die entsprechenden Meldungshandler-Funktion aufrufen. Klicken Sie bei jedem Befehl der aufgerufene Code möglicherweise Ihre oder möglicherweise der Frameworks.

Diese Anordnung ist Programmierern, die Erfahrung mit herkömmlichen Programmierung für Windows oder ereignisgesteuerte Programmierung vertraut.

Sie werden in verwandten Themen lesen, was das Framework als er initialisiert und führt die Anwendung und dann bereinigt, wenn die Anwendung beendet wird. Es wird auch erläutert, in dem der Code, den Sie schreiben in passt.

Weitere Informationen finden Sie unter [Klasse CWinApp: die Anwendungsklasse](../mfc/cwinapp-the-application-class.md) und [Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="see-also"></a>Siehe auch

[Erstellen im Framework](../mfc/building-on-the-framework.md)

