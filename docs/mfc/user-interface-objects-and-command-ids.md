---
title: Benutzeroberflächenobjekte und Befehls-IDs
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
ms.openlocfilehash: 508e7076797d48e0940b509afa3b94a7b766ebf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615357"
---
# <a name="user-interface-objects-and-command-ids"></a>Benutzeroberflächenobjekte und Befehls-IDs

Menüelemente, Symbolleistenschaltflächen und Tastenkombinationen sind "Benutzeroberfläche-Objekte" Befehle generieren kann. Jedes dieser Objekte der Benutzeroberfläche verfügt über eine ID. Ein Benutzeroberflächen-Objekt können Sie mit einem Befehl zugeordnet, indem Sie das Objekt und der Befehl die gleiche ID zuweisen. Siehe [Nachrichten](../mfc/messages.md), Befehle werden als besondere Nachrichten implementiert. Die Abbildung "Befehle im Framework" unten zeigt, wie Befehle in der vom Framework verwaltet. Wenn ein Objekt für die Benutzeroberfläche generiert einen Befehl, z. B. `ID_EDIT_CLEAR_ALL`, eines der Objekte in Ihrer Anwendung behandelt den Befehl, in der folgenden Abbildung dargestellt des Document-Objekts `OnEditClearAll` -Funktion über die meldungszuordnung des Dokuments aufgerufen wird.

![Befehle im Framework](../mfc/media/vc385p1.gif "vc385p1") Befehle im Framework

Die Abbildung "Befehl aktualisieren im Framework" unten zeigt, wie MFC für Objekte wie z. B. Menüelemente und Symbolleisten-Schaltflächen der Benutzeroberfläche aktualisiert. Bevor ein Menü angezeigt wird, oder während der Leerlaufschleife im Fall von Symbolleisten-Schaltflächen, MFC einen Update-Befehl leitet. In der folgenden Abbildung, das Document-Objekt aufruft, die Update-Befehlshandler, `OnUpdateEditClearAll`, zum Aktivieren oder deaktivieren das UI-Objekt.

![Befehl in das Framework aktualisiert](../mfc/media/vc385p2.png "vc385p2") -Befehl zu aktualisieren, in das Framework

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

