---
title: "Einstellungen f&#252;r das Statussteuerelement | Microsoft Docs"
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
  - "CProgressCtrl-Klasse, Einstellungen"
  - "Statussteuerelemente [C++], Einstellungen"
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einstellungen f&#252;r das Statussteuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die grundlegenden Einstellungen zum Statussteuerelement \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) ist der Bereich und die aktuelle Position.  Der Bereich stellt die gesamte Dauer des Vorgangs dar.  Die aktuelle Position stellt den Status dar, den die Anwendung beim Abschließen des Vorgangs ausgeführt hat.  Alle Änderungen an der Bereichs\- oder Positionsursache das Statussteuerelement, um selbst neu zu zeichnen.  
  
 Standardmäßig wird der Bereich bis 0 festgelegt \- 100 und die Startposition wird 0 festgelegt.  Um die Strombereicheinstellungen für das Statussteuerelement abzurufen, verwenden Sie die [GetRange](../Topic/CProgressCtrl::GetRange.md)\-Memberfunktion.  Um den Bereich zu ändern, verwenden Sie die [SetRange](../Topic/CProgressCtrl::SetRange.md)\-Memberfunktion.  
  
 Um die Position festlegen, verwenden Sie [SetPos](../Topic/CProgressCtrl::SetPos.md).  Um die aktuelle Position ohne einen neuen Wert anzugeben abzurufen, verwenden Sie [GetPos](../Topic/CProgressCtrl::GetPos.md).  Sie möchten beispielsweise auf Status des aktuellen Vorgang einfach abfragen.  
  
 Um zu treten die aktuelle Position des Statussteuerelements, verwenden Sie [StepIt](../Topic/CProgressCtrl::StepIt.md).  Um die Menge aller Schritte festzulegen, verwenden Sie [SetStep](../Topic/CProgressCtrl::SetStep.md)  
  
## Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)