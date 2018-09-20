---
title: Rahmenfensterklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac60fb8d1b12708c7e64a91beb224ca436e5005
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404526"
---
# <a name="frame-window-classes"></a>Rahmenfensterklassen

Jede Anwendung hat eine "Hauptrahmenfenster," desktop-Fenster, die in der Regel den Namen der Anwendung in der Beschriftung. Jedes Dokument ist normalerweise auf eine "Dokumentrahmenfenster." Einem Dokumentrahmenfenster enthält mindestens eine Ansicht, die die Daten des Dokuments enthält.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>Frame-Windows-SDI und MDI-Anwendungen

Bei einer SDI-Anwendung besteht ein Rahmenfenster von Klasse abgeleitet [CFrameWnd](../mfc/reference/cframewnd-class.md). Dieses Fenster ist sowohl das Hauptrahmenfenster und die Dokumentrahmenfenster. Für eine MDI-Anwendung, das Hauptrahmenfenster von Klasse abgeleitet ist [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), und die Frame-Dokumentfenster, das untergeordneten MDI-Fenster sind, werden von der Klasse abgeleitet [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Verwenden Sie die Frame-Window-Klasse, oder davon abgeleitet

Diese Klassen bieten die meisten Rahmenfenster Funktionen, die Sie für Ihre Anwendungen benötigen. Unter normalen Umständen ist das Standardverhalten und die Darstellung, die sie bereitstellen, die Ihren Anforderungen entsprechend. Wenn Sie zusätzliche Funktionalität benötigen, leiten Sie von diesen Klassen.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Vom Anwendungs-Assistenten erstellte Rahmenfensterklassen](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)

- [Ändern der Stile eines mit MFC erstellten Fensters](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>Siehe auch

[Rahmenfenster](../mfc/frame-windows.md)

