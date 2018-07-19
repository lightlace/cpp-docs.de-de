---
title: Zerstören von Rahmenfenstern | Microsoft Docs
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
ms.openlocfilehash: 81182c0e5633e19126d3036b5793de7658ad3d2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343475"
---
# <a name="destroying-frame-windows"></a>Zerstören von Rahmenfenstern
Die MFC-Grundstruktur verwaltet fensterzerstörung sowie das Erstellen von diesen Fenstern Framework Dokumente und Ansichten zugeordnet. Wenn Sie zusätzliche Fenster erstellen, können Sie sie zerstören.  
  
 In dem Framework, wenn der Benutzer das Rahmenfenster des Fensters Standardeinstellung schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) Ereignishandler ruft [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), führt die Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich ruft der virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung von `PostNcDestroy` löscht die C++-Fensterobjekt. Sie sollten niemals verwenden, die C++ **löschen** -Operator in einem Rahmenfenster. Verwenden Sie stattdessen `DestroyWindow`.  
  
 Wenn das Hauptfenster geschlossen wird, wird die Anwendung geschlossen. Wenn es nicht gespeicherte Dokumente geändert werden, wird das Framework zeigt ein Meldungsfeld gefragt, ob die Dokumente gespeichert werden soll, und stellt sicher, dass die entsprechenden Dokumente gespeichert werden, bei Bedarf.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

