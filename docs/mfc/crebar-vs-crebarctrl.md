---
title: "CReBar im Vergleich zu CReBarCtrl"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CReBar"
  - "CReBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CReBar-Klasse, kontra CReBarCtrl"
  - "GetReBarCtrl-Klasse"
  - "rebar-Steuerelemente, CReBarCtrl-Klasse"
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CReBar im Vergleich zu CReBarCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt zwei Klassen, um Infoleisten zu erstellen: [CReBar](../mfc/reference/crebar-class.md) und [CReBarCtrl](../mfc/reference/crebarctrl-class.md) \(das die API des allgemeinen Windows\-Steuerelements umschließt\).  **CReBar** stellt alle Funktionen der Infoleistengemeinsamen allgemeinen ToolTip\-Steuerelement, und sie behandelt viele der erforderlichen Einstellungen und Strukturen der allgemeinen Steuerelement für Sie.  
  
 `CReBarCtrl` ist eine Wrapperklasse für das Win32\-Infoleiste\-Steuerelement und daher möglicherweise einfacher zu implementieren, wenn Sie nicht beabsichtigen, die Infoleiste in die MFC\-Architektur zu integrieren.  Wenn Sie planen, `CReBarCtrl` verwenden und die Infoleiste in die MFC\-Architektur zu integrieren, müssen Sie zusätzliche darauf achten, um Infoleiste\-Steuerelement\-Manipulationen zu MFC mitzuteilen.  Diese Kommunikation ist nicht schwierig; ist es jedoch weitere Arbeitschritte, die nicht erforderlich ist, wenn Sie **CReBar** verwenden.  
  
 Visual C\+\+ bietet zwei Möglichkeiten, die Infoleistengemeinsame allgemeinen ToolTip\-Steuerelement zu nutzen.  
  
-   Stellen Sie die Infoleiste mit **CReBar**, und rufen Sie anschließend [CReBar::GetReBarCtrl](../Topic/CReBar::GetReBarCtrl.md) auf, um den Zugriff auf den `CReBarCtrl`\-Memberfunktionen abzurufen.  
  
    > [!NOTE]
    >  `CReBar::GetReBarCtrl` ist eine Inlinedatei Memberfunktion, die den Zeiger des **this** Infoleistenobjekts umwandeln.  Dies bedeutet, dass die Laufzeit der Funktionsaufruf keinen Aufwand hat.  
  
-   Stellen Sie die Infoleiste mit [CReBarCtrl](../mfc/reference/crebarctrl-class.md)\-Konstruktors erstellt.  
  
 Jede Methode gibt Ihnen Zugriff in Memberfunktionen des Infoleiste\-Steuerelements.  Wenn Sie `CReBar::GetReBarCtrl` aufrufen, wird ein Verweis auf ein `CReBarCtrl`\-Objekt zurück, sodass Sie alle verwenden festlegen von Memberfunktionen.  Siehe [CReBar](../mfc/reference/crebar-class.md) zu Informationen über das Erstellen und das Erstellen einer Infoleiste mit **CReBar**.  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)