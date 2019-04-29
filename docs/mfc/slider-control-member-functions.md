---
title: Memberfunktionen des Schieberegler-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: a88dd1a49eb928261393a4473ee7eb53628c607a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307430"
---
# <a name="slider-control-member-functions"></a>Memberfunktionen des Schieberegler-Steuerelements

Eine Anwendung kann den Schieberegler-Steuerelements-Member-Funktionen zum Abrufen von Informationen über das Schiebereglersteuerelement aufrufen ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) und seine Eigenschaften zu ändern.

Die Position des Schiebereglers (d. h. der Wert, der der Benutzer hat ausgewählt) abzurufen, verwenden Sie die [GetPos](../mfc/reference/csliderctrl-class.md#getpos) Member-Funktion. Verwenden Sie zum Festlegen der Position des Schiebereglers die [Memberfunktion SetPos](../mfc/reference/csliderctrl-class.md#setpos) Member-Funktion. Zu einem beliebigen Zeitpunkt können Sie die `VerifyPos` Member-Funktion, um sicherzustellen, dass der Schieberegler zwischen den minimalen und maximalen Werten ist.

Das Spektrum ein Schieberegler-Steuerelement ist der Satz von zusammenhängenden Werten, die das Schieberegler-Steuerelement darstellen kann. Die meisten Anwendungen verwenden die [SetRange](../mfc/reference/csliderctrl-class.md#setrange) Memberfunktion versucht, den Datumsbereich ein Schieberegler-Steuerelement festlegen, wenn er erstmals erstellt wird. Anwendungen können den Bereich dynamisch ändern, nachdem mithilfe der Schieberegler-Steuerelement erstellt wurde die [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) und [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) Memberfunktionen. Eine Anwendung, die können den Bereich in der Regel dynamisch geändert werden, ruft die endgültige bereichseinstellungen ab, wenn der Benutzer die Verwendung mit dem Schiebereglersteuerelement beendet. Um diese Einstellungen abzurufen, verwenden Sie die [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), und [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) Memberfunktionen.

Eine Anwendung kann den TBS_AUTOTICKS-Stil verwenden, haben Sie ein Schieberegler-Steuerelement-Teilstriche, die automatisch angezeigt. Wenn eine Anwendung die Position oder die Häufigkeit der Teilstriche zu steuern muss, kann jedoch eine Reihe von Memberfunktionen verwendet werden.

Um die Position eines Teilstrichs festgelegt, der eine Anwendung kann mithilfe der [SetTic](../mfc/reference/csliderctrl-class.md#settic) Member-Funktion. Die [Memberfunktion SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) Member-Funktion kann eine Anwendung zum Teilstriche markiert, in regelmäßigen Abständen in das Schieberegler-Steuerelement-Bereich angezeigt. Beispielsweise kann die Anwendung diese Memberfunktion verwenden, zum Anzeigen von nur 10 Teilstrichen in einem Bereich von 1 bis 100.

Verwenden Sie zum Abrufen des Indexes in den Bereich eines Teilstrichs für die [Memberfunktion GetTic](../mfc/reference/csliderctrl-class.md#gettic) Member-Funktion. Die [Memberfunktion GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) Memberfunktion Ruft ein Array dieser Indizes ab. Verwenden Sie zum Abrufen der Position eines Teilstrichs in Clientkoordinaten der [Memberfunktion GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) Member-Funktion. Eine Anwendung kann die Anzahl von Teilstrichen abrufen, mithilfe der [Memberfunktion GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) Member-Funktion.

Die [Memberfunktion ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) Memberfunktion entfernt alle von Teilstrichen für ein Schieberegler-Steuerelement.

Ein Schieberegler-Steuerelement die Größe bestimmt, wie weit der Schieberegler bewegt wird, wenn eine Anwendung eine Benachrichtigung TB_LINEDOWN oder TB_LINEUP empfängt. Bestimmt, die Seitengröße die Antwort auf die TB_PAGEDOWN und TB_PAGEUP Benachrichtigungsnachrichten erstellt werden. Anwendungen abrufen und Festlegen der Größenwerte Seite und Zeile mithilfe der [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), und [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) Memberfunktionen.

Eine Anwendung kann Memberfunktionen verwenden, um die Abmessungen des Schieberegler-Steuerelement abzurufen. Die [Memberfunktion GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) Memberfunktion Ruft das umschließende Rechteck für den Schieberegler. Die [Memberfunktion GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) Memberfunktion Ruft das umschließende Rechteck für den Kanal für das Schieberegler-Steuerelement. (Der Kanal ist der Bereich über das Verschieben des Schiebereglers, und die Hervorhebung enthält, wenn ein Bereich markiert ist.)

Wenn ein Schieberegler-Steuerelement den TBS_ENABLESELRANGE Stil verfügt, kann der Benutzer einen zusammenhängenden Wertebereich daraus auswählen. Eine Reihe von Memberfunktionen kann den Auswahlbereich dynamisch angepasst werden. Die [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) Memberfunktion legt fest, die Start- und Endposition einer Auswahl. Wenn der Benutzer einen Auswahlbereich festlegen abgeschlossen ist, kann eine Anwendung die Einstellungen abrufen, indem Sie mit der [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) Member-Funktion. Auswahl des Benutzers verwenden, um die [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
