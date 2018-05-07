---
title: Verwenden eines Standardsteuerelements als untergeordnetes Fenster | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50d21675d913211026a2077a0830b7d8ed1225c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-a-common-control-as-a-child-window"></a>Verwenden eines Standardsteuerelements als untergeordnetes Fenster
Alle allgemeinen Windows-Steuerelemente können als untergeordnetes Fenster von einem anderen Fenster verwendet werden. Das folgende Verfahren beschreibt, wie ein allgemeines Steuerelement dynamisch zu erstellen, und klicken Sie dann mit ihm gearbeitet wird.  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>Verwenden ein Standardsteuerelements als untergeordnetes Fenster  
  
1.  Definieren Sie das Steuerelement in der zugehörigen Klasse oder der Handler.  
  
2.  Verwenden des Steuerelements: f Überschreibung von der [CWnd:: Create](../mfc/reference/cwnd-class.md#create) Methode, um das Windows-Steuerelement zu erstellen.  
  
3.  Nachdem das Steuerelement erstellt wurde (so früh wie die `OnCreate` Handler Wenn Sie eine Unterklasse des Steuerelements), können Sie das Steuerelement über seine Memberfunktionen ändern. Siehe die Beschreibung der einzelnen Steuerelementen zur [Steuerelemente](../mfc/controls-mfc.md) ausführliche Informationen über Methoden.  
  
4.  Wenn Sie mit dem Steuerelement fertig sind, verwenden Sie [CWnd:: DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) zerstört das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

