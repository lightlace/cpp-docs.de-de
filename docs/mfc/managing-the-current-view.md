---
title: Verwalten der aktuellen Ansicht | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323903d2e1285a4ee697bbd9d0c3a29c2e1248d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="managing-the-current-view"></a>Verwalten der aktuellen Ansicht
Im Rahmen der Standardimplementierung von Rahmenfenstern der nachverfolgt ein Rahmenfensters eine derzeit aktive Ansicht. Wenn das Rahmenfenster mehr als eine Ansicht, z. B. in einem Splitterfenster enthält ist die aktuelle Ansicht die aktuellste Ansicht verwendet. Die aktive Ansicht ist unabhängig von dem aktiven Fenster in Windows oder den aktuellen Eingabefokus.  
  
 Wenn die aktive Ansicht ändert, ändert das Framework benachrichtigt die aktuelle Ansicht durch Aufrufen seiner [OnActivateView](../mfc/reference/cview-class.md#onactivateview) Memberfunktion. Ist ersichtlich, ob die Sicht wird aktiviert oder deaktiviert werden, indem Sie untersuchen `OnActivateView`des `bActivate` Parameter. Standardmäßig `OnActivateView` legt den Fokus auf die aktuelle Ansicht auf Aktivierung fest. Sie können außer Kraft setzen `OnActivateView` auszuführenden keine spezielle verarbeiten, wenn die Ansicht deaktiviert oder erneut aktiviert wird. Beispielsweise empfiehlt es sich um besondere visuelle Hinweise zur Unterscheidung der der aktiven Ansicht von inaktiven Ansichten bereitzustellen.  
  
 Ein Framefenster leitet Befehle aus, um die aktuelle (aktive) Ansicht aus, wie in beschrieben [Befehlsrouting](../mfc/command-routing.md), als Teil des standardbefehlsroutings.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

