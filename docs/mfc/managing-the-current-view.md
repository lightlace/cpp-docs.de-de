---
title: Verwalten der aktuellen Ansicht | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1510b005f452174acfe8ad65ae3f66cf8aafaa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="managing-the-current-view"></a>Verwalten der aktuellen Ansicht
Im Rahmen der Standardimplementierung von Rahmenfenstern der nachverfolgt ein Rahmenfensters eine derzeit aktive Ansicht. Wenn das Rahmenfenster mehr als eine Ansicht, z. B. in einem Splitterfenster enthält ist die aktuelle Ansicht die aktuellste Ansicht verwendet. Die aktive Ansicht ist unabhängig von dem aktiven Fenster in Windows oder den aktuellen Eingabefokus.  
  
 Wenn die aktive Ansicht ändert, ändert das Framework benachrichtigt die aktuelle Ansicht durch Aufrufen seiner [OnActivateView](../mfc/reference/cview-class.md#onactivateview) Memberfunktion. Ist ersichtlich, ob die Sicht wird aktiviert oder deaktiviert werden, indem Sie untersuchen `OnActivateView`des `bActivate` Parameter. Standardmäßig `OnActivateView` legt den Fokus auf die aktuelle Ansicht auf Aktivierung fest. Sie können außer Kraft setzen `OnActivateView` auszuführenden keine spezielle verarbeiten, wenn die Ansicht deaktiviert oder erneut aktiviert wird. Beispielsweise empfiehlt es sich um besondere visuelle Hinweise zur Unterscheidung der der aktiven Ansicht von inaktiven Ansichten bereitzustellen.  
  
 Ein Framefenster leitet Befehle aus, um die aktuelle (aktive) Ansicht aus, wie in beschrieben [Befehlsrouting](../mfc/command-routing.md), als Teil des standardbefehlsroutings.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

