---
title: "Hinzufügen von Elementen zum Headersteuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de62d534da103f17df113b04b88021561739cfc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-items-to-the-header-control"></a>Hinzufügen von Elementen zum Headersteuerelement
Nach dem Erstellen der Headersteuerelement ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) in das übergeordnete Fenster, wie viele Headerelemente hinzufügen, "" wie erforderlich: in der Regel eine pro Spalte.  
  
### <a name="to-add-a-header-item"></a>Ein Headerelement hinzufügen  
  
1.  Vorbereiten einer [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) Struktur.  
  
2.  Rufen Sie [InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), die Struktur übergeben wird.  
  
3.  Wiederholen Sie die Schritte 1 und 2 für zusätzliche Objekte gibt.  
  
 Weitere Informationen finden Sie unter [Hinzufügen eines Elements zu einem Headersteuerelement](http://msdn.microsoft.com/library/windows/desktop/bb775238) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

