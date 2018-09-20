---
title: Benutzeroberflächenobjekte und Befehls-IDs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8a61699ddd2c48e36bdfd5936fb4ab7aa56e0a9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416122"
---
# <a name="user-interface-objects-and-command-ids"></a>Benutzeroberflächenobjekte und Befehls-IDs

Menüelemente, Symbolleistenschaltflächen und Tastenkombinationen sind "Benutzeroberfläche-Objekte" Befehle generieren kann. Jedes dieser Objekte der Benutzeroberfläche verfügt über eine ID. Ein Benutzeroberflächen-Objekt können Sie mit einem Befehl zugeordnet, indem Sie das Objekt und der Befehl die gleiche ID zuweisen. Siehe [Nachrichten](../mfc/messages.md), Befehle werden als besondere Nachrichten implementiert. Die Abbildung "Befehle im Framework" unten zeigt, wie Befehle in der vom Framework verwaltet. Wenn ein Objekt für die Benutzeroberfläche generiert einen Befehl, z. B. `ID_EDIT_CLEAR_ALL`, eines der Objekte in Ihrer Anwendung behandelt den Befehl, in der folgenden Abbildung dargestellt des Document-Objekts `OnEditClearAll` -Funktion über die meldungszuordnung des Dokuments aufgerufen wird.

![Befehle im Framework](../mfc/media/vc385p1.gif "vc385p1") Befehle im Framework

Die Abbildung "Befehl aktualisieren im Framework" unten zeigt, wie MFC für Objekte wie z. B. Menüelemente und Symbolleisten-Schaltflächen der Benutzeroberfläche aktualisiert. Bevor ein Menü angezeigt wird, oder während der Leerlaufschleife im Fall von Symbolleisten-Schaltflächen, MFC einen Update-Befehl leitet. In der folgenden Abbildung, das Document-Objekt aufruft, die Update-Befehlshandler, `OnUpdateEditClearAll`, zum Aktivieren oder deaktivieren das UI-Objekt.

![Befehl in das Framework aktualisiert](../mfc/media/vc385p2.png "vc385p2") -Befehl zu aktualisieren, in das Framework

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

