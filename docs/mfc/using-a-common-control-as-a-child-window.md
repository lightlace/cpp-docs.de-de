---
title: Verwenden eines Standardsteuerelements als untergeordnetes Fenster | Microsoft Docs
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
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 475c769bf09c0693c04780712b85884ae7c48862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

