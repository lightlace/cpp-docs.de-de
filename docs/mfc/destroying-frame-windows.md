---
title: "Zerstören von Rahmenfenstern | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PostNcDestroy
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1cbd96f5044626c7c3c07e8fca115c2b1dca8cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-frame-windows"></a>Zerstören von Rahmenfenstern
Die MFC-Grundstruktur verwaltet fensterzerstörung sowie das Erstellen von diesen Fenstern Framework Dokumente und Ansichten zugeordnet. Wenn Sie zusätzliche Fenster erstellen, können Sie sie zerstören.  
  
 In dem Framework, wenn der Benutzer das Rahmenfenster des Fensters Standardeinstellung schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) Ereignishandler ruft [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), führt die Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich ruft der virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung von `PostNcDestroy` löscht die C++-Fensterobjekt. Sie sollten niemals verwenden, die C++ **löschen** -Operator in einem Rahmenfenster. Verwenden Sie stattdessen `DestroyWindow`.  
  
 Wenn das Hauptfenster geschlossen wird, wird die Anwendung geschlossen. Wenn es nicht gespeicherte Dokumente geändert werden, wird das Framework zeigt ein Meldungsfeld gefragt, ob die Dokumente gespeichert werden soll, und stellt sicher, dass die entsprechenden Dokumente gespeichert werden, bei Bedarf.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Dokument Rahmenfenster](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

