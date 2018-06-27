---
title: Stile der Schieberegler-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f76fbe9f85d978a5c2865b48720588b620508a07
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951051"
---
# <a name="slider-control-styles"></a>Stile der Schieberegler-Steuerelemente
Schieberegler-Steuerelemente ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) haben eine vertikale oder horizontale Ausrichtung. Teilstriche auf beiden Seiten über verfügen beide Seiten oder keines von beiden. Sie können auch verwendet werden, um einen Bereich aufeinander folgender Werte anzugeben. Mithilfe des Schiebereglers Steuerelementtypen, die Sie angeben, wenn Sie das Schieberegler-Steuerelement erstellen, werden diese Eigenschaften gesteuert.  
  
 Die Formate TBS_HORZ und TBS_VERT Bestimmen der Ausrichtung des Schieberegler-Steuerelements. Wenn Sie keine Ausrichtung angeben, wird das Schieberegler-Steuerelement horizontal ausgerichtet.  
  
 Das TBS_AUTOTICKS-Format erstellt ein Schieberegler-Steuerelement, das in dessen Bereich der Werte ein Teilstrichs für jede inkrementelle verfügt. Diese Teilstriche werden automatisch hinzugefügt, beim Aufrufen der [SetRange](../mfc/reference/csliderctrl-class.md#setrange) Memberfunktion. Wenn Sie TBS_AUTOTICKS nicht angeben, können Sie Memberfunktionen, z. B. [SetTic](../mfc/reference/csliderctrl-class.md#settic) und [Memberfunktion SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), um anzugeben, die Positionen der Teilstriche. Um ein Schieberegler-Steuerelement zu erstellen, die keine Teilstriche angezeigt werden, können Sie das Format TBS_NOTICKS verwenden.  
  
 Sie können die Teilstriche auf einer oder beiden Seiten des Schieberegler-Steuerelements anzeigen. Für horizontale Schieberegler-Steuerelemente können Sie die Formatvorlage TBS_BOTTOM oder das TBS_TOP angeben. Für den vertikalen Schieberegler-Steuerelemente können Sie das Format TBS_RIGHT oder TBS_LEFT angeben. (TBS_BOTTOM und TBS_RIGHT sind die Standardeinstellungen.) Geben Sie für die Teilstriche auf beiden Seiten des Schieberegler-Steuerelements in alle Ausrichtung den TBS_BOTH-Stil.  
  
 Ein Schieberegler-Steuerelement kann einen Auswahlbereich angezeigt werden, nur, wenn Sie die Formatvorlage TBS_ENABLESELRANGE angeben, bei der Erstellung. Wenn ein Schieberegler-Steuerelement dieses Format aufweist, wird die Teilstriche an den Positionen, Start- und Enddaten eines Auswahlbereichs werden als Dreiecke (statt senkrechte Striche) angezeigt, und Auswahlbereich wird hervorgehoben. Beispielsweise können Auswahl Bereiche in einer einfachen planungsanwendung nützlich sein. Der Benutzer konnte wählen Sie einen Bereich von Teilstrichen für Stunden eines Tages zu einem Zeitpunkt geplante Besprechung zu identifizieren.  
  
 Standardmäßig ändert sich die Länge des Schiebereglers ein Schieberegler-Steuerelement die Auswahl Bereichs ändert. Wenn das Schieberegler-Steuerelement das TBS_FIXEDLENGTH-Format aufweist, bleibt die Länge des Schiebereglers, selbst wenn der Auswahlbereich ändert. Ein Schieberegler-Steuerelement, das den Stil TBS_NOTHUMB verfügt umfasst einen Schieberegler nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

