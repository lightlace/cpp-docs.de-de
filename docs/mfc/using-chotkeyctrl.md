---
title: Verwenden von CHotKeyCtrl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CHotKeyCtrl
dev_langs:
- C++
helpviewer_keywords:
- keys, hot and CHotKeyCtrl
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3678d95ff0748c1854e509d898dfa89778c9a5f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-chotkeyctrl"></a>Verwenden von CHotKeyCtrl
Eines Abkürzungstasten-Steuerelements, dargestellt durch die Klasse [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md), ist ein Fenster, in dem eine Textdarstellung der Tastenkombination angezeigt, der Benutzer, z. B. STRG + UMSCHALT + Q eingibt. Er verwaltet auch eine interne Darstellung dieses Schlüssels in Form von einem virtuellem Tastencode und eine Gruppe von Flags, die UMSCHALT-Status darstellen. Die Abkürzungstasten-Steuerelements wird nicht tatsächlich die Abkürzungstaste festgelegt – bis zu das Programm wird auf diese Weise. (Eine Liste der standardmäßigen virtuellen Tastencodes, finden Sie unter Winuser.h.)  
  
 Verwenden eines Abkürzungstasten-Steuerelements zum Abrufen der Benutzereingabe für welche Abkürzungstaste ein Fenster oder ein Thread zugeordnet werden soll. Abkürzungstasten-Steuerelemente werden häufig in Dialogfeldern verwendet, z. B. möglicherweise angezeigt wird, wenn Sie gefragt werden, die Benutzer eine Abkürzungstaste zugewiesen. Es ist Aufgabe des Programms, zum Abrufen der Werte, die im laufenden Systembetrieb Schlüssel aus der Abkürzungstasten-Steuerelements beschreibt, und rufen Sie die entsprechenden Funktionen, um ein Fenster oder Thread der Abkürzungstaste zuzuordnen.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Verwenden eines Abkürzungstasten-Steuerelements](../mfc/using-a-hot-key-control.md)  
  
-   [Festlegen einer Abkürzungstaste](../mfc/setting-a-hot-key.md)  
  
-   [Globale Abkürzungstasten](../mfc/global-hot-keys.md)  
  
-   [Threadspezifische Abkürzungstasten](../mfc/thread-specific-hot-keys.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente](../mfc/controls-mfc.md)

