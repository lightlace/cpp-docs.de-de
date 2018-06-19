---
title: Struktur der Auswahl in einem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb08fcbb1bd77cc80fdbe014d8c9e8a0851254d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385897"
---
# <a name="tree-control-item-selection"></a>Wechseln der Auswahl in einem Struktursteuerelement
Wenn die Auswahl Änderungen von einem Element für ein anderes, ein Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) sendet [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) und [eine TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) benachrichtigungsmeldungen. Beide Benachrichtigungen enthalten einen Wert, der angibt, ob die Änderung das Ergebnis ein Mausklick oder eine Tastenkombination ist. Die Benachrichtigungen umfassen auch Informationen über das Element, das Zustand wechselt die Auswahl und das Element, das die Auswahl entfernt wird. Diese Informationen können Sie Attribute festgelegt, die von den Auswahlzustand des Elements abhängen. Zurückgeben von **"true"** als Antwort auf **TVN_SELCHANGING** wird verhindert, dass die Auswahl nicht ändern; zurückgeben **"false"** ermöglicht die Änderung.  
  
 Eine Anwendung kann die Auswahl ändern, durch Aufrufen der [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

