---
title: Memberfunktionen des Schieberegler-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3793ca47aa0537d5ca8d6858c165fc2c5ac64943
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383444"
---
# <a name="slider-control-member-functions"></a>Memberfunktionen des Schieberegler-Steuerelements
Eine Anwendung kann den Schieberegler Memberfunktionen zum Abrufen von Informationen über das Schieberegler-Steuerelement des Steuerelements aufrufen ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) und deren Eigenschaften zu ändern.  
  
 Die Position des Schiebereglers (d. h. der Wert, der der Benutzer hat ausgewählt) abzurufen, verwenden Sie die [GetPos](../mfc/reference/csliderctrl-class.md#getpos) Memberfunktion. Verwenden Sie zum Festlegen der Position des Schiebereglers die [Memberfunktion SetPos](../mfc/reference/csliderctrl-class.md#setpos) Memberfunktion. Zu einem beliebigen Zeitpunkt können Sie die `VerifyPos` Member-Funktion, um sicherzustellen, dass der Schieberegler zwischen den minimalen und maximalen Werten ist.  
  
 Der Bereich des Schieberegler-Steuerelements ist der Satz aufeinander folgender Werte, die das Schieberegler-Steuerelement darstellen kann. Die meisten Anwendungen verwenden die [SetRange](../mfc/reference/csliderctrl-class.md#setrange) Memberfunktion versucht, den Datumsbereich ein Schieberegler-Steuerelement festlegen, wenn der Dienst erstmalig erstellt wird. Anwendungen können den Bereich dynamisch ändern, nachdem das Schieberegler-Steuerelement mit erstellt wurde die [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) und [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) Memberfunktionen. Eine Anwendung, die können den Bereich in der Regel dynamisch geändert werden, ruft die endgültige Bereich-Einstellungen ab, wenn der Benutzer die Verwendung mit dem Schiebereglersteuerelement beendet. Um diese Einstellungen abzurufen, verwenden Sie die [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), und [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) Memberfunktionen.  
  
 Eine Anwendung kann mithilfe der `TBS_AUTOTICKS` Formatvorlage auf ein Schieberegler-Steuerelement-Teilstriche, die automatisch angezeigt, verfügen. Wenn eine Anwendung die Position oder die Häufigkeit der Teilstriche steuern muss, kann jedoch eine Anzahl von Memberfunktionen verwendet werden.  
  
 Um die Position eines Teilstrichs festzulegen, können Sie eine Anwendung die [SetTic](../mfc/reference/csliderctrl-class.md#settic) Memberfunktion. Die [Memberfunktion SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) Memberfunktion ermöglicht einer Anwendung, Teilstriche Markierungen festgelegt, die in regelmäßigen Abständen im Bereich für das Schieberegler-Steuerelement angezeigt werden. Beispielsweise kann die Anwendung diese Memberfunktion verwenden, in einem Bereich von 1 bis 100 nur 10 Teilstriche angezeigt.  
  
 Verwenden Sie zum Abrufen des Indexes im Bereich eines Teilstrichs für die [Memberfunktion GetTic](../mfc/reference/csliderctrl-class.md#gettic) Memberfunktion. Die [Memberfunktion GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) Memberfunktion Ruft ein Array dieser Indizes ab. Verwenden Sie die Position eines Teilstrichs in Clientkoordinaten, Abrufen der [Memberfunktion GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) Memberfunktion. Eine Anwendung kann die Anzahl der Teilstriche abrufen, mithilfe der [Memberfunktion GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) Memberfunktion.  
  
 Die [Memberfunktion ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) Memberfunktion entfernt alle von Teilstrichen für ein Schieberegler-Steuerelement.  
  
 Größe für das ein Schieberegler-Steuerelement bestimmt, wie weit der Schieberegler verschoben wird, wenn eine Anwendung empfängt eine **TB_LINEDOWN** oder **TB_LINEUP** benachrichtigungsmeldung. Auf ähnliche Weise die Seitengröße bestimmt die Antwort auf die **TB_PAGEDOWN** und **TB_PAGEUP** benachrichtigungsmeldungen. Anwendungen abrufen und Festlegen der Größenwerte Seite und Zeile mit der [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), und [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) Memberfunktionen.  
  
 Memberfunktionen können eine Anwendung die Dimensionen der Schieberegler-Steuerelement abzurufen. Die [Memberfunktion GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) Memberfunktion Ruft das umschließende Rechteck für den Schieberegler. Die [Memberfunktion GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) Memberfunktion Ruft das umschließende Rechteck für das Schieberegler-Steuerelement-Kanal. (Der Kanal ist der Bereich, über die verschiebt des Schiebereglers, und der die Hervorhebung enthält, wenn ein Bereich ausgewählt ist).  
  
 Wenn ein Schiebereglersteuerelement verfügt über die `TBS_ENABLESELRANGE` Formatvorlage, der Benutzer kann einen zusammenhängenden Wertebereich daraus auswählen. Eine Anzahl von Memberfunktionen kann den Auswahlbereich dynamisch angepasst werden. Die [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) Memberfunktion legt fest, die Start- und Endposition einer Auswahl. Wenn der Benutzer einen Auswahlbereich festlegen abgeschlossen ist, kann eine Anwendung mithilfe der Einstellungen Abrufen der [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) Memberfunktion. Auswahl des Benutzers verwenden, um die [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

