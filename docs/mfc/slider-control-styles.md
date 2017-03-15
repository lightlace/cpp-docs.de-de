---
title: "Stile der Schieberegler-Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl-Klasse, Stile"
  - "Schieberegler-Steuerelemente, Stile"
  - "Stile, CSliderCtrl"
  - "Stile, Schieberegler-Steuerelemente"
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Stile der Schieberegler-Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Slider\-Steuerelementen \([CSliderCtrl](../mfc/reference/csliderctrl-class.md)\) können eine vertikale oder horizontale Ausrichtung haben.  Sie können Teilstriche, beide Seiten oder keine auf beiden Seiten verfügen.  Sie können auch verwendet werden, um einen Bereich von nachfolgenden Werten an.  Diese Eigenschaften werden gesteuert, indem Schieberegler\-Steuerelement\-Formate verwendet, die Sie angeben, wann Sie das Schieberegler\-Steuerelement erstellen.  
  
 Die `TBS_HORZ` und `TBS_VERT` Stile bestimmen die Ausrichtung des Schieberegler\-Steuerelements.  Wenn Sie keine Ausrichtung angeben, wird das Schieberegler\-Steuerelement horizontal ausgerichtet.  
  
 Das Format `TBS_AUTOTICKS` erstellt ein Schieberegler\-Steuerelement, das einen Teilstrich für jedes Inkrement in seinem Wertebereich hat.  Teilstriche Diese werden automatisch hinzugefügt, wenn Sie die [SetRange](../Topic/CSliderCtrl::SetRange.md)\-Memberfunktion aufrufen.  Wenn Sie `TBS_AUTOTICKS` nicht angeben, können Sie Memberfunktionen, wie [SetTic](../Topic/CSliderCtrl::SetTic.md) und [SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md) verwenden, um die Position der Teilstriche anzugeben.  Um ein Schieberegler\-Steuerelement erstellt das nicht Teilstriche anzeigt, können Sie das Format `TBS_NOTICKS` verwenden.  
  
 Sie können einzelnen oder Teilstriche auf beiden Seiten des Schieberegler\-Steuerelements anzeigen.  Eine horizontale Slider\-Steuerelementen können Sie dem `TBS_BOTTOM` oder `TBS_TOP` Format angeben.  Eine vertikale Slider\-Steuerelementen können Sie dem `TBS_RIGHT` oder `TBS_LEFT` Format angeben. \(`TBS_BOTTOM` und `TBS_RIGHT` sind die Standardeinstellungen.\) Die Teilstriche auf beiden Seiten des Slider\-Steuerelement in jeder Ausrichtung, geben Sie den `TBS_BOTH` Format an.  
  
 Ein \- kann ein Auswahlbereich nur dann anzeigen, wenn Sie dem Stil `TBS_ENABLESELRANGE` angeben, wenn Sie ihn erstellen.  Wenn ein Schieberegler\-Steuerelement dieses Format enthält, werden die Teilstriche auf dem Starten und den Zielpositionen eines Auswahlbereichs als Dreiecke \(anstelle des vertikalen Bindestrich\) angezeigt und der Auswahlbereich wird hervorgehoben.  Beispielweise kann Auswahlbereiche in einfachem Planungsanwendung nützlich.  Der Benutzer kann einen Bereich von Ticks entsprechend Stunden an einem Tag auswählen, um eine Zeit der planmäßigen Sitzung zu identifizieren.  
  
 Standardmäßig unterscheidet sich die Länge des Schiebereglers eines Schieberegler\-Steuerelements, wie der Auswahlbereich ändert.  Wenn das Schieberegler\-Steuerelement das **TBS\_FIXEDLENGTH** Stil verfügt, wird die Länge des Schiebereglers genauso, auch wenn der Auswahlbereich ändert.  Ein Schieberegler\-Steuerelement, das **TBS\_NOTHUMB** Format hat, enthält keinen Schieberegler.  
  
## Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)