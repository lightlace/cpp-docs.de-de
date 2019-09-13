---
title: Meldungszuordnungen (MFC)
ms.date: 09/07/2019
helpviewer_keywords:
- message maps [MFC], MFC
- Windows messages [MFC], message maps
- messages [MFC], Windows
- MFC, messages
ms.assetid: 3f9855e4-9d7d-4b64-8f3f-a19ea3cf79ba
ms.openlocfilehash: 4305d9b1db297eebcb189d2fad98b8c634ed1133
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908039"
---
# <a name="message-maps-mfc"></a>Meldungszuordnungen (MFC)

In diesem Abschnitt des Verweises werden alle Nachrichten Zuordnungs [Makros](../../mfc/reference/message-map-macros-mfc.md) und alle [CWnd](../../mfc/reference/cwnd-class.md) -Nachrichten Zuordnungs Einträge sowie die zugehörigen Prototypen der Element Funktionen aufgelistet:

|Kategorie|Beschreibung|
|--------------|-----------------|
|\_Befehlsnachrichten Handler|Verarbeitet `WM_COMMAND` Nachrichten, die von der Benutzermenü Auswahl oder Menü Zugriffstasten generiert werden.|
|[Meldungshandler für Benachrichtigungen von untergeordneten Fenstern](../../mfc/reference/child-window-notification-message-handlers.md)|Verarbeiten Benachrichtigungen von untergeordneten Fenstern.|
|[WM_-Meldungs Handler](../../mfc/reference/handlers-for-wm-messages.md)|Verarbeiten `WM_` von Nachrichten, `WM_PAINT`z. b.|
|[Benutzerdefinierte Meldungs Handler](../../mfc/reference/user-defined-handlers.md)|Verarbeiten benutzerdefinierte Meldungen.|

(Eine Erläuterung der Terminologie und Konventionen, die in dieser Referenz verwendet werden, finden [Sie unter How to use the Message Map Cross-Reference](../../mfc/reference/how-to-use-the-message-map-cross-reference.md).)

Da Windows ein meldungsorientiertes Betriebssystem ist, bezieht sich ein Großteil der Programmierung für die Windows-Umgebung auf die Verarbeitung von Meldungen. Bei jeder Tastatureingabe bzw. jedem Mausklick wird eine Meldung an die Anwendung gesendet, die das Ereignis dann verarbeiten muss.

Microsoft Foundation Class-Bibliothek bietet ein Programmiermodell, das für die meldungsbasierte Programmierung optimiert wurde. In diesem Modell wird mithilfe von "Meldungszuordnungen" festgelegt, welche Funktionen die verschiedenen Meldungen für eine bestimmte Klasse verarbeiten. Meldungszuordnungen enthalten ein oder mehrere Makros, die angeben, welche Meldungen von welchen Funktionen verarbeitet werden. Eine Meldungszuordnung, die ein `ON_COMMAND`-Makro enthält, kann z. B. wie folgt aussehen:

[!code-cpp[NVC_MFCMessageMaps#16](../../mfc/reference/codesnippet/cpp/message-maps-mfc_1.cpp)]

Das `ON_COMMAND`-Makro wird zur Verarbeitung von Befehlsmeldungen verwendet, die von Menüs, Schaltflächen und Zugriffstasten generiert werden. [Makros](../../mfc/reference/message-map-macros-mfc.md) sind verfügbar, um Folgendes zuzuordnen:

## <a name="windows-messages"></a>Windows-Meldungen

- Steuerelementbenachrichtigungen

- Benutzerdefinierte Meldungen

## <a name="command-messages"></a>Befehlsmeldungen

- Registrierte benutzerdefinierte Meldungen

- Meldungen zur Benutzeroberflächen-Aktualisierung

## <a name="ranges-of-messages"></a>Meldungsbereiche

- Befehle

- Aktualisierungshandlermeldungen

- Steuerelementbenachrichtigungen

Meldungszuordnungsmakros sind zwar wichtig, Sie müssen sie im Allgemeinen jedoch nicht direkt verwenden. Dies liegt daran, dass der [Klassen-Assistent](mfc-class-wizard.md) automatisch Meldungs Zuordnungs Einträge in den Quelldateien erstellt, wenn Sie ihn verwenden, um Nachrichten Behandlungs Funktionen mit Nachrichten zuzuordnen. Wenn Sie einen Meldungs Zuordnungs Eintrag bearbeiten oder hinzufügen möchten, können Sie den Klassen-Assistenten verwenden.

> [!NOTE]
>  Der Klassen-Assistent unterstützt keine Nachrichten Zuordnungs Bereiche. Sie müssen diese Meldungszuordnungseinträge selbst schreiben.

Meldungszuordnungen sind jedoch ein wichtiger Teil der Microsoft Foundation Class-Bibliothek, und Sie sollten ihre Funktionsweise kennen. Weitere Informationen finden Sie in der zur Verfügung stehenden Dokumentation.

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)
