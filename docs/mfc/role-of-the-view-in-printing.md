---
title: Die Rolle der Ansicht beim Drucken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], printing
- OnDraw method [MFC], and printing
- printing [MFC], OnDraw method [MFC]
- printing [MFC], views
- CView class [MFC], role in printing
- printing views [MFC]
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c78756ea84df66b77f71d8f8ad8d0b9dfa1a6c9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377525"
---
# <a name="role-of-the-view-in-printing"></a>Die Rolle der Ansicht beim Drucken

Die Ansicht spielt auch zwei wichtige Rollen in seine zugeordnete Dokument zu drucken.

Die Ansicht:

- Verwendet die gleichen [OnDraw](../mfc/reference/cview-class.md#ondraw) Code zum Zeichnen auf den Drucker, die auf dem Bildschirm gezeichnet werden soll.

- Verwaltet die Unterteilung des Dokuments in Seiten für das Drucken.

Weitere Informationen zum Drucken und zur Rolle von der Ansicht beim Drucken, finden Sie unter [drucken und Druckvorschau](../mfc/printing-and-print-preview.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von Ansichten](../mfc/using-views.md)

