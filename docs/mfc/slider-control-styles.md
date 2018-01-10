---
title: Stile der Schieberegler-Steuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747f5d55821c6911e80087ebbad65b2169e6fc49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-styles"></a>Stile der Schieberegler-Steuerelemente
Schieberegler-Steuerelemente ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) haben eine vertikale oder horizontale Ausrichtung. Teilstriche auf beiden Seiten über verfügen beide Seiten oder keines von beiden. Sie können auch verwendet werden, um einen Bereich aufeinander folgender Werte anzugeben. Mithilfe des Schiebereglers Steuerelementtypen, die Sie angeben, wenn Sie das Schieberegler-Steuerelement erstellen, werden diese Eigenschaften gesteuert.  
  
 Die `TBS_HORZ` und `TBS_VERT` Stile zu ermitteln, die Ausrichtung des Schieberegler-Steuerelements. Wenn Sie keine Ausrichtung angeben, wird das Schieberegler-Steuerelement horizontal ausgerichtet.  
  
 Die `TBS_AUTOTICKS` Stil erstellt ein Schieberegler-Steuerelement, das in dessen Bereich der Werte ein Teilstrichs für jede inkrementelle verfügt. Diese Teilstriche werden automatisch hinzugefügt, beim Aufrufen der [SetRange](../mfc/reference/csliderctrl-class.md#setrange) Memberfunktion. Wenn Sie keinen angeben `TBS_AUTOTICKS`, Sie verwenden die Memberfunktionen, z. B. [SetTic](../mfc/reference/csliderctrl-class.md#settic) und [Memberfunktion SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), um anzugeben, die Positionen der Teilstriche. Um ein Schieberegler-Steuerelement zu erstellen, die keine Teilstriche angezeigt werden, können Sie die `TBS_NOTICKS` Stil.  
  
 Sie können die Teilstriche auf einer oder beiden Seiten des Schieberegler-Steuerelements anzeigen. Horizontaler Schieberegler-Steuerelemente können Sie angeben der `TBS_BOTTOM` oder `TBS_TOP` Stil. Für den vertikalen Schieberegler-Steuerelemente können Sie angeben der `TBS_RIGHT` oder `TBS_LEFT` Stil. (`TBS_BOTTOM` und `TBS_RIGHT` sind die Standardeinstellungen.) Geben Sie für die Teilstriche auf beiden Seiten des Schieberegler-Steuerelements in alle Ausrichtung, die `TBS_BOTH` Stil.  
  
 Ein Schieberegler-Steuerelement kann einen Auswahlbereich nur angezeigt, wenn Sie angeben, die `TBS_ENABLESELRANGE` Format zuzuweisen, wenn Sie ihn erstellen. Wenn ein Schieberegler-Steuerelement dieses Format aufweist, wird die Teilstriche an den Positionen, Start- und Enddaten eines Auswahlbereichs werden als Dreiecke (statt senkrechte Striche) angezeigt, und Auswahlbereich wird hervorgehoben. Beispielsweise können Auswahl Bereiche in einer einfachen planungsanwendung nützlich sein. Der Benutzer konnte wählen Sie einen Bereich von Teilstrichen für Stunden eines Tages zu einem Zeitpunkt geplante Besprechung zu identifizieren.  
  
 Standardmäßig ändert sich die Länge des Schiebereglers ein Schieberegler-Steuerelement die Auswahl Bereichs ändert. Wenn das Schieberegler-Steuerelement verfügt über die **TBS_FIXEDLENGTH** Stil, die Länge des Schiebereglers bleibt unverändert, auch wenn der Auswahlbereich ändert. Ein Schiebereglersteuerelement mit der **TBS_NOTHUMB** Stil einen Schieberegler nicht einschließt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

