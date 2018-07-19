---
title: Verwenden eines Animationssteuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d6b6b07040fbece5fae24fb2ca6be8985695eb0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950536"
---
# <a name="using-an-animation-control"></a>Verwenden eines Animationssteuerelements
Typische Verwendung eines Animationssteuerelements entspricht dem folgenden Muster:  
  
-   Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sie müssen eine [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) Member in der Dialogfeldklasse, die die Animation-Steuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/canimatectrl-class.md#create) Memberfunktion beim Erstellen des Steuerelements als untergeordnetes Fenster von einem beliebigen Fenster.  
  
-   Laden ein AVI-Videoclips in die Animationssteuerelements durch Aufrufen der [öffnen](../mfc/reference/canimatectrl-class.md#open) Memberfunktion. Animation-Steuerelement in einem Dialogfeld eine gute hierfür ist, in der Dialogfeldklasse [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.  
  
-   Geben Sie den Clip durch Aufrufen der [wiedergeben](../mfc/reference/canimatectrl-class.md#play) Memberfunktion. Animation-Steuerelement in einem Dialogfeld eine gute hierfür ist, in der Dialogfeldklasse `OnInitDialog` Funktion. Aufrufen von `Play` ist nicht erforderlich, wenn die Animationssteuerelements festgelegten ACS_AUTOPLAY-Format aufweist.  
  
-   Wenn Sie Teile des Clips anzeigen oder wiedergeben Frame nach dem anderen, verwenden möchten die `Seek` Memberfunktion. Zum Beenden der Wiedergabe des Clip verwenden die `Stop` Memberfunktion.  
  
-   Wenn Sie nicht beabsichtigen, das Steuerelement sofort zu zerstören, entfernen Sie den Clip aus dem Speicher durch Aufrufen der `Close` Memberfunktion.  
  
-   Wenn die Animationssteuerelement in einem Dialogfeld ist es und `CAnimateCtrl` Objekt wird automatisch zerstört werden. Wenn nicht der Fall, Sie sicherstellen, dass sowohl im Steuerelement müssen und dem `CAnimateCtrl` Objekt ordnungsgemäß zerstört werden. Zerstören das Steuerelement automatisch schließt AVI-Videoclips.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

