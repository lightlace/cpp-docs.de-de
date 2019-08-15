---
title: Struktursteuerelementstile
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
ms.openlocfilehash: f5f28025d0349e9bcd95aba50d4110d304fed376
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510941"
---
# <a name="tree-control-styles"></a>Struktursteuerelementstile

Struktur Steuerelement-Stile ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) steuern Aspekte der Darstellung eines Struktur Steuer Elements. Sie legen die anfänglichen Stile fest, wenn Sie das Struktur Steuerelement erstellen. Sie können die Stile abrufen und ändern, nachdem Sie das Struktur Steuerelement mithilfe der Windows-Funktionen [GetWindowLong](/windows/win32/api/winuser/nf-winuser-getwindowlongw) und [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) erstellt und **GWL_STYLE** für den *nIndex* -Parameter angegeben haben. Eine umfassende Liste der Stile finden Sie Unterstruktur [Ansicht-Steuerelement Fenster Stile](/windows/win32/Controls/tree-view-control-window-styles) in der Windows SDK.

Der **TVS_HASLINES** -Stil erweitert die grafische Darstellung der Hierarchie eines Struktur Steuer Elements durch das Zeichnen von Linien, die untergeordnete Elemente mit dem entsprechenden übergeordneten Element verknüpfen. Dieser Stil verknüpft keine Elemente am Stamm der Hierarchie. Zu diesem Zweck müssen Sie die Stile **TVS_HASLINES** und **TVS_LINESATROOT** kombinieren.

Der Benutzer kann die Liste der untergeordneten Elemente eines übergeordneten Elements durch Doppelklicken auf das übergeordnete Element erweitern oder reduzieren. Ein Struktur Steuerelement, das über den **TVS_SINGLEEXPAND** -Stil verfügt, bewirkt, dass das ausgewählte Element erweitert wird und das Element nicht ausgewählt wird. Wenn mit dem Mauszeiger auf das ausgewählte Element geklickt wird und dieses Element geschlossen ist, wird es erweitert. Wenn beim Öffnen auf das ausgewählte Element geklickt wird, wird es reduziert.

Ein Struktur Steuerelement mit dem **TVS_HASBUTTONS** -Stil fügt eine Schaltfläche auf der linken Seite jedes übergeordneten Elements hinzu. Der Benutzer kann auf die Schaltfläche klicken, um die untergeordneten Elemente als Alternative zum Doppelklicken auf das übergeordnete Element zu erweitern oder zu reduzieren. **TVS_HASBUTTONS** fügt den Elementen im Stamm der Hierarchie keine Schaltflächen hinzu. Zu diesem Zweck müssen Sie **TVS_HASLINES**, **TVS_LINESATROOT**und **TVS_HASBUTTONS**kombinieren.

Der **TVS_EDITLABELS** -Stil ermöglicht dem Benutzer das Bearbeiten der Bezeichnungen von Struktur Steuerelementen. Weitere Informationen zum Bearbeiten von Bezeichnungen finden Sie unter Bearbeiten von Struktur [Steuer](../mfc/tree-control-label-editing.md) Element Bezeichnungen weiter unten in diesem Thema.

Der **TVS_NOTOOLTIPS** -Stil deaktiviert das automatische QuickInfo-Feature von Strukturansicht-Steuerelementen. Diese Funktion zeigt automatisch eine QuickInfo an, die den Titel des Elements unter dem Mauszeiger enthält, wenn der gesamte Titel derzeit nicht sichtbar ist.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
