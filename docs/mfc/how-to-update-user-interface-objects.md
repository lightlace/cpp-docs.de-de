---
title: 'Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten'
ms.date: 11/04/2016
helpviewer_keywords:
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- user interface objects [MFC]
- update handlers [MFC]
- enabling UI elements [MFC]
- disabling menus [MFC]
- updating user-interface objects [MFC]
- disabling UI elements [MFC]
- commands [MFC], updating UI
- enabling menus [MFC]
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
ms.openlocfilehash: 0dee9bb48c11cf061af60ebaf9a80c0123d339be
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289701"
---
# <a name="how-to-update-user-interface-objects"></a>Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten

Menüelemente und Symbolleisten-Schaltflächen müssen in der Regel mehr als einem Zustand auf. Beispielsweise wird ein Menüelement (abgeblendet) abgeblendet, im aktuellen Kontext nicht verfügbar ist. Menüelemente können auch aktiviert oder deaktiviert sein. Eine Symbolleisten-Schaltfläche kann auch deaktiviert werden, wenn nicht verfügbar oder kann überprüft werden.

Die den Status der diese Elemente logischerweise Programmieren von Bedingungen sich ändern, wenn ein Menüelement ein Befehls generiert, das von behandelt wird, z. B. ein Dokument aktualisiert wird, ist es sinnvoll, das Dokument, das das Menüelement zu aktualisieren. Das Dokument enthält wahrscheinlich die Informationen, die auf der das Update basiert.

Wenn ein Befehl mehrere UI-Objekte (z. B. ein Menüelement und eine Symbolleisten-Schaltfläche) enthält, werden sowohl auf die gleiche Handlerfunktion weitergeleitet. Diese kapselt Ihren Aktualisierungscode der Benutzeroberfläche für alle entsprechenden Benutzeroberflächen-Objekte an einem Ort.

Das Framework bietet eine einfache Schnittstelle zum automatischen Aktualisieren von Benutzeroberflächenobjekten. Sie können auswählen, der Aktualisierung auf andere Weise, aber die bereitgestellte Schnittstelle ist effizient und einfach zu verwenden.

Die folgenden Themen erläutern die Verwendung von updatehandler:

- [Wann müssen updatehandler aufgerufen werden?](../mfc/when-update-handlers-are-called.md)

- [Die ON_UPDATE_COMMAND_UI-Makro](../mfc/on-update-command-ui-macro.md)

- [Die CCmdUI-Klasse](../mfc/the-ccmdui-class.md)

## <a name="see-also"></a>Siehe auch

[Menüs](../mfc/menus-mfc.md)
