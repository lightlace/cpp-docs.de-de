---
title: Wann müssen CWnd-Objekte initialisiert werden?
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: c75745547846fbf6c7e01ecf473d4d6f366bd264
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548550"
---
# <a name="when-to-initialize-cwnd-objects"></a>Wann müssen CWnd-Objekte initialisiert werden?

Sie erstellen Ihre eigenen untergeordnete Windows oder rufen Sie alle Windows-API-Funktionen in den Konstruktor der können keinem `CWnd`-abgeleitetes Objekt. Grund hierfür ist die `HWND` für die `CWnd` Objekt noch nicht erstellt wurde. Die meisten Windows-spezifische Initialisierung, z. B. das Hinzufügen von untergeordneten Fenster muss ausgeführt werden, eine [OnCreate](../mfc/reference/cwnd-class.md#oncreate) Message-Handler.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen eines Dokuments Rahmenfenster](../mfc/creating-document-frame-windows.md)

- [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

