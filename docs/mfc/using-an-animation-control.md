---
title: Verwenden eines Animationssteuerelements | Microsoft Docs
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
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38523c832f4a30f247bd3e1d0b8318f44f5c47b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-animation-control"></a>Verwenden eines Animationssteuerelements
Typische Verwendung eines Animationssteuerelements entspricht dem folgenden Muster:  
  
-   Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sie müssen eine [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) Member in der Dialogfeldklasse, die die Animation-Steuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/canimatectrl-class.md#create) Memberfunktion beim Erstellen des Steuerelements als untergeordnetes Fenster von einem beliebigen Fenster.  
  
-   Laden ein AVI-Videoclips in die Animationssteuerelements durch Aufrufen der [öffnen](../mfc/reference/canimatectrl-class.md#open) Memberfunktion. Animation-Steuerelement in einem Dialogfeld eine gute hierfür ist, in der Dialogfeldklasse [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.  
  
-   Geben Sie den Clip durch Aufrufen der [wiedergeben](../mfc/reference/canimatectrl-class.md#play) Memberfunktion. Animation-Steuerelement in einem Dialogfeld eine gute hierfür ist, in der Dialogfeldklasse **OnInitDialog** Funktion. Aufrufen von **wiedergeben** ist nicht erforderlich, wenn das Animationssteuerelement verfügt die `ACS_AUTOPLAY` Satz formatieren.  
  
-   Wenn Sie Teile des Clips anzeigen oder wiedergeben Frame nach dem anderen, verwenden möchten die `Seek` Memberfunktion. Zum Beenden der Wiedergabe des Clip verwenden die `Stop` Memberfunktion.  
  
-   Wenn Sie nicht beabsichtigen, das Steuerelement sofort zu zerstören, entfernen Sie den Clip aus dem Speicher durch Aufrufen der **schließen** Memberfunktion.  
  
-   Wenn die Animationssteuerelement in einem Dialogfeld ist es und `CAnimateCtrl` Objekt wird automatisch zerstört werden. Wenn nicht der Fall, Sie sicherstellen, dass sowohl im Steuerelement müssen und dem `CAnimateCtrl` Objekt ordnungsgemäß zerstört werden. Zerstören das Steuerelement automatisch schließt AVI-Videoclips.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

