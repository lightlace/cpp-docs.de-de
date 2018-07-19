---
title: Hinzufügen von Elementen zum Headersteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69d64265a94df2770e3a234ab992130b4809f9e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342734"
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

