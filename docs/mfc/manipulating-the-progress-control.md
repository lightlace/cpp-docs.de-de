---
title: "Bearbeiten des Statussteuerelements"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuern von Statussteuerelementen"
  - "CProgressCtrl-Klasse, Bearbeiten"
  - "CProgressCtrl-Klasse, Verwenden"
  - "CProgressCtrl-Klasse, Arbeiten mit"
  - "Statussteuerelemente [C++], Bearbeiten"
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Bearbeiten des Statussteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt drei Möglichkeiten, die aktuelle Position eines Statussteuerelements \([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)\) zu ändern.  
  
-   Die Position kann durch eine Voreinstellungsinkrementmenge geändert werden.  
  
-   Die Position kann durch eine beliebige Größe geändert werden.  
  
-   Die Position kann zu einem bestimmten Wert geändert werden.  
  
### Um die Position um eine voreingestellte ändern betragen Sie  
  
1.  Verwenden Sie die [SetStep](../Topic/CProgressCtrl::SetStep.md)\-Memberfunktion, um die Inkrementmenge festzulegen.  Der Standardwert beträgt 10.  Dieser Wert wird üblicherweise als einer der anfänglichen Einstellungen für das Steuerelement festgelegt.  Der Schrittwert kann negativ sein.  
  
2.  Verwenden Sie die [StepIt](../Topic/CProgressCtrl::StepIt.md)\-Memberfunktion, um die Position inkrementiert werden.  Dies bewirkt, dass Steuerelemente sich neu zu zeichnen.  
  
    > [!NOTE]
    >  `StepIt` verursacht die Position um.  Beispielsweise einen Bereich von 1 gegeben \- 100, ein Schritt von 20 und eine Position 90, `StepIt` legen die Position auf 10. fest.  
  
### Um die Position um eine beliebige Größe ändern  
  
1.  Verwenden Sie die [OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)\-Memberfunktion, um die Position zu ändern.  `OffsetPos` akzeptiert negative Werte.  
  
    > [!NOTE]
    >  `OffsetPos`, außer `StepIt`, wird nicht die Position ein.  Die neue Position wird, innerhalb des Bereichs bleiben angepasst.  
  
### Um die Position auf einen bestimmten Wert ändern  
  
1.  Verwenden Sie die [SetPos](../Topic/CProgressCtrl::SetPos.md)\-Memberfunktion, um die Position auf einen bestimmten Wert festzulegen.  Bei Bedarf wird die neue Position, im Bereich angepasst zu sein.  
  
 In der Regel wird das Statussteuerelement nur für Ausgabe verwendet.  Um die aktuelle Position ohne einen neuen Wert anzugeben abzurufen, verwenden Sie [GetPos](../Topic/CProgressCtrl::GetPos.md).  
  
## Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)