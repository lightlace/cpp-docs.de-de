---
title: "Memberfunktionen des Schieberegler-Steuerelements | Microsoft Docs"
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
  - "CSliderCtrl-Klasse, Methoden"
  - "Schieberegler-Steuerelemente, Memberfunktionen"
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Memberfunktionen des Schieberegler-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Anwendung kann die Memberfunktionen des Slider\-Steuerelements aufrufen, um Informationen über das Schieberegler\-Steuerelement \([CSliderCtrl](../mfc/reference/csliderctrl-class.md)\) abzurufen und dessen Eigenschaften ändern.  
  
 Um die Position des Schiebereglers \(das heißt, der Wert, den der Benutzer ausgewählt hat\) abzurufen, verwenden Sie die [GetPos](../Topic/CSliderCtrl::GetPos.md)\-Memberfunktion.  Um die Position des Schiebereglers festzulegen, verwenden Sie die [SetPos](../Topic/CSliderCtrl::SetPos.md)\-Memberfunktion.  Sie können jederzeit die `VerifyPos`\-Memberfunktion verwenden, um zu überprüfen, ob der Schieberegler zwischen den Mindest\- und Höchstwerten ist.  
  
 Der Gültigkeitsbereich eines Schieberegler\-Steuerelements ist der Satz von zusammenhängenden Werte, die das Schieberegler\-Steuerelement darstellen kann.  Die meisten Anwendungen verwenden die Memberfunktion [SetRange](../Topic/CSliderCtrl::SetRange.md), um den Bereich eines "Slider" \- Steuerelements festzulegen, wenn es zuerst erstellt wird.  Anwendungen können den Bereich nach dem Slider\-Steuerelement dynamisch ändern erstellt wurde, indem sie die [SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md) und [SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md) verwenden Memberfunktionen.  Eine Anwendung, die den dynamisch können normalerweise geändert werden, Bereich, ruft die abschließenden Bereichseinstellungen ab, wenn der Benutzer das Arbeiten mit dem Slider\-Steuerelement beendet wurde.  Um diese Einstellungen abzurufen, verwenden Sie [GetRange](../Topic/CSliderCtrl::GetRange.md), [GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md) und [GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)\-Memberfunktionen.  
  
 Eine Anwendung kann das Format `TBS_AUTOTICKS` verwenden, um die Teilstriche eines "Slider" \- Steuerelements automatisch angezeigt haben.  Wenn eine Anwendung die Position festlegen muss, oder Anzahl der Teilstriche können jedoch einige Memberfunktionen verwendet werden.  
  
 Um die Position eines Teilstrichs festzulegen, kann eine Anwendung die Memberfunktion [SetTic](../Topic/CSliderCtrl::SetTic.md) verwenden.  Die Memberfunktion [SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md) ermöglicht es einer Anwendung, Teilstriche festzulegen, die in regelmäßigen Abständen im Bereich des Schieberegler\-Steuerelements werden.  Beispielsweise kann die Anwendung diese Memberfunktion verwenden, um nur 10 Teilstriche in einem Bereich von 1 bis 100 anzuzeigen.  
  
 Um den Index im Bereich entsprechend einem Teilstrich abzurufen, verwenden Sie die [GetTic](../Topic/CSliderCtrl::GetTic.md)\-Memberfunktion.  Die Memberfunktion [GetTicArray](../Topic/CSliderCtrl::GetTicArray.md) ruft ein Array dieser Indizes abhängig.  Um die Position eines Teilstrichs, in Clientkoordinaten abzurufen, verwenden Sie die [GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)\-Memberfunktion.  Eine Anwendung kann die Anzahl der Zeiteinheiten abrufen, indem sie die [GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)\-Memberfunktion verwendet.  
  
 Die Memberfunktion [ClearTics](../Topic/CSliderCtrl::ClearTics.md) entfernt alle Teilstriche eines Schieberegler\-Steuerelements.  
  
 Eine Zeilengröße des Slider\-Steuerelements bestimmt, wie weit sich der Schieberegler verschoben wird, wenn eine Anwendung eine Benachrichtigung empfängt **TB\_LINEDOWN** oder **TB\_LINEUP**.  Auf ähnliche Weise bestimmt die Seitengröße die Antwort zu den **TB\_PAGEDOWN** und **TB\_PAGEUP** Benachrichtigungsmeldungen.  Anwendungen können den Zeilen\- und Seitengrößenwerte abrufen und festlegen, indem sie [GetLineSize](../Topic/CSliderCtrl::GetLineSize.md), [SetLineSize](../Topic/CSliderCtrl::SetLineSize.md), [GetPageSize](../Topic/CSliderCtrl::GetPageSize.md) und [SetPageSize](../Topic/CSliderCtrl::SetPageSize.md) verwenden Memberfunktionen.  
  
 Eine Anwendung kann Memberfunktionen verwenden, um die Abmessungen eines Schieberegler\-Steuerelements abzurufen.  Die Memberfunktion [GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md) ruft das umschließende Rechteck für den Schieberegler ab.  Die Memberfunktion [GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md) ruft das umschließende Rechteck für den Steuerkanal des Slider\-Steuerelements ab. \(Der Channel ist der Bereich, über denen der Schieberegler verschoben wird und die Hervorhebung enthält, wenn der Bereich ausgewählt ist.\)  
  
 Wenn ein Schieberegler\-Steuerelement das Format `TBS_ENABLESELRANGE` hat, kann der Benutzer einen Bereich von zusammenhängenden Werten davon auswählen.  Einige Memberfunktionen können den dynamisch angepasst werden Auswahlbereich.  Die Memberfunktion [SetSelection](../Topic/CSliderCtrl::SetSelection.md) legt das Anfangs\- und Endposition einer Auswahl fest.  Wenn der Benutzer beendet, ein Auswahlbereich festzulegen, kann eine Anwendung die Einstellungen abrufen, indem sie die [GetSelection](../Topic/CSliderCtrl::GetSelection.md)\-Memberfunktion verwendet.  Um die Auswahl eines Benutzers löschen, verwenden Sie die [ClearSel](../Topic/CSliderCtrl::ClearSel.md)\-Memberfunktion.  
  
## Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)