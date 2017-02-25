---
title: "MFC-ActiveX-Steuerelemente: Zur&#252;ckgeben von Fehlercodes aus einer Methode | Microsoft Docs"
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
  - "Fehler [C++], ActiveX-Steuerelementfehlercodes"
  - "FireError-Methode"
  - "GetNotSupported-Methode"
  - "MFC-ActiveX-Steuerelemente, Fehlercodes"
  - "SCODE, MFC-ActiveX-Steuerelemente"
  - "SetNotSupported-Methode, Verwenden"
  - "ThrowError-Methode"
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Zur&#252;ckgeben von Fehlercodes aus einer Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie Fehlercodes aus einer ActiveX\-Steuerelement\-Methode zurückgibt.  
  
 Um anzugeben dass ein Fehler in einer Methode erfolgt ist, können Sie die Memberfunktion [COleControl::ThrowError](../Topic/COleControl::ThrowError.md) verwenden, die `SCODE` \(Statuscode\) als Parameter akzeptiert.  Sie können vordefinierte `SCODE` verwenden oder eine eigene definiert.  
  
> [!NOTE]
>  `ThrowError` gilt, nur als Mittel zur Rückgabe eines Fehlers aus einer Eigenschaft verwendet werden abrufen oder festlegen Funktion oder eine Automatisierung Methode.  Dies sind die einzigen vorkommen, dass der entsprechende Ausnahmehandler auf dem Stapel vorhanden ist.  
  
 Hilfsfunktionen sind für die gängigsten vordefinierte `SCODE`s, wie [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md) und [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
 Eine Liste vordefinierter `SCODE`s und zum Definieren von benutzerdefiniertem `SCODE`s, finden Sie im Abschnitt [Fehlerbehandlung im ActiveX\-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX\-Steuerelemente: Weiterführende Themen.  
  
 Weitere Informationen über Berichterstellungsausnahmen in anderen Bereichen des Codes, finden Sie unter [COleControl::FireError](../Topic/COleControl::FireError.md) und im Abschnitt [Fehlerbehandlung im ActiveX\-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX\-Steuerelemente: Weiterführende Themen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)