---
title: Zerstören von Frame Windows | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 742ea2fedff2e4f044e46242a4152c12855ab15e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396154"
---
# <a name="destroying-frame-windows"></a>Zerstören von Rahmenfenstern

MFC-Framework verwaltet fensterzerstörung sowie die Erstellung für diese Windows Framework Dokumente und Ansichten zugeordnet. Wenn Sie zusätzliche Fenster erstellen, sind Sie verantwortlich für das sie löschen.

Im Framework, wenn der Benutzer das Rahmenfenster, des Fensters Standardmäßig schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) handleraufrufen [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), geschieht das Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich Ruft die virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung `PostNcDestroy` löscht das C++-Fensterobjekt. Verwenden Sie niemals die C++ **löschen** Operators für ein Rahmenfenster. Verwenden Sie stattdessen `DestroyWindow`.

Wenn das Hauptfenster geschlossen wird, wird die Anwendung geschlossen. Wenn es nicht gespeicherte Dokumente geändert werden, wird das Framework zeigt ein Meldungsfeld, um anzufordern, wenn die Dokumente gespeichert werden soll, und stellt sicher, dass die entsprechenden Dokumente gespeichert werden, falls erforderlich.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen eines Dokuments Rahmenfenster](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

