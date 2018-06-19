---
title: Aktuelle Auswahl in einem Rich-Edit-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 782984bc53bc16f8dc89e4e705811fef24b8931e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345009"
---
# <a name="current-selection-in-a-rich-edit-control"></a>Die aktuelle Auswahl in einem RichEdit-Steuerelement
Der Benutzer kann Text in einem rich-Edit-Steuerelement auswählen ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) mit der Maus oder Tastatur. Die aktuelle Auswahl ist der Bereich der ausgewählten Zeichen, oder die Position der Einfügemarke, wenn keine Zeichen ausgewählt sind. Eine Anwendung kann Abrufen von Informationen über die aktuelle Auswahl, legen Sie die aktuelle Auswahl, bestimmen, wenn die aktuelle Auswahl ändert und Einblenden / Ausblenden der Auswahl hervorgehoben.  
  
 Um die aktuelle Auswahl in einem rich-Edit-Steuerelement zu ermitteln, verwenden die [Memberfunktion GetSel](../mfc/reference/cricheditctrl-class.md#getsel) Memberfunktion. Um die aktuelle Auswahl festzulegen, verwenden die [Memberfunktion SetSel](../mfc/reference/cricheditctrl-class.md#setsel) Memberfunktion. Die [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur wird mit diesen Funktionen verwendet, um einen Bereich von Zeichen anzugeben. Abrufen von Informationen über den Inhalt der aktuellen Auswahl können Sie die [Memberfunktion GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype) Memberfunktion.  
  
 Standardmäßig wird ein rich-Edit-Steuerelement zeigt und blendet die Markierung erhält und den Fokus verliert. Sie können ein- oder die auswahlmarkierung jederzeit ausblenden, indem die [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection) Memberfunktion. Beispielsweise könnte eine Anwendung eine Meldungssuche (Dialogfeld), um Text in einem rich-Edit-Steuerelement suchen bereitstellen. Die Anwendung könnte übereinstimmenden Text auswählen, ohne das Dialogfeld zu schließen, die in diesem Fall müssen sie verwenden `HideSelection` markieren.  
  
 Verwenden Sie zum Abrufen des markierten Texts in einem rich-Edit-Steuerelement die [Memberfunktion GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext) Memberfunktion. Der Text wird an das angegebene Zeichenarray kopiert. Sie müssen sicherstellen, dass das Array zum Speichern des markierten Texts plus ein abschließendes Nullzeichen groß genug ist.  
  
 Sie können nach einer Zeichenfolge in einem rich-Edit-Steuerelement suchen, mit der [FindText](../mfc/reference/cricheditctrl-class.md#findtext) Memberfunktion der [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) Struktur, die mit dieser Funktion verwendet gibt den Textbereich zum Durchsuchen und die zu suchende Zeichenfolge. Sie können auch die entsprechenden Optionen angeben, als gibt an, ob bei der Suche Groß-/Kleinschreibung beachtet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

