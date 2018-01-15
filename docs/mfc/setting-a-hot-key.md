---
title: "Festlegen einer Abkürzungstaste | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cd52fca8415196fc1393cc49fe7830f6ca2cfd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setting-a-hot-key"></a>Festlegen einer Abkürzungstaste
Die Anwendung kann mithilfe den Informationen von einer Abkürzungstaste ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) Steuerelement in einer von zwei Methoden:  
  
-   Richten Sie eine globale Abkürzungstaste für die Aktivierung eines nicht untergeordneten Fensters durch Senden einer [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284) Nachricht an das Fenster aktiviert werden.  
  
-   Richten Sie eine threadspezifische Abkürzungstaste durch Aufrufen der Windows-Funktion [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHotKeyCtrl](../mfc/using-chotkeyctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

