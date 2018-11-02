---
title: Behandeln von reflektierten Meldungen
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 9b580c0c8b8fc970d69f5c57f69bbbbe65e22497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449867"
---
# <a name="handling-reflected-messages"></a>Behandeln von reflektierten Meldungen

Nachricht, die Reflektion können Sie die Meldungen für ein Steuerelement, z. B. behandeln **WM_CTLCOLOR**, **WM_COMMAND**, und **WM_NOTIFY**, innerhalb des Steuerelements selbst. Dadurch wird das Steuerelement mehr unabhängige und übertragbare. Der Mechanismus funktioniert mit Windows-Standardsteuerelemente sowie mit ActiveX-Steuerelementen (früher OLE-Steuerelemente).

Nachricht, die Reflektion können Sie die Wiederverwendung Ihrer `CWnd`-leichter abgeleiteten Klassen. Reflektion funktioniert über Message [CWnd:: OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), mithilfe von speziellen **ON_XXX_REFLECT** message-Zuordnungseinträge: z. B. **ON_CTLCOLOR_REFLECT** und **ON_CONTROL_REFLECT**. [Technischer Hinweis 62](../mfc/tn062-message-reflection-for-windows-controls.md) Meldungsreflektion ausführlicher erläutert.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

- [Erfahren Sie mehr über Meldungsreflektion](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Implementieren von Meldungsreflektion für ein allgemeines Steuerelement](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Implementieren von Meldungsreflektion für ein ActiveX-Steuerelement](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>Siehe auch

[Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
