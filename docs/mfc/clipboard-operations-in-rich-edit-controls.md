---
title: Zwischenablageoperationen in RichEdit-Edit-Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e831a76a491d1025ae45117d40362a85523742da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341283"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>Zwischenablageoperationen in RichEdit-Steuerelementen
Ihre Anwendung kann den Inhalt der Zwischenablage in ein rich-Edit-Steuerelement einfügen ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) mit den am besten verfügbaren Zwischenablageformat oder einem bestimmten Zwischenablageformat. Sie können auch bestimmen, ob ein rich-Edit-Steuerelement kann ein Format der Zwischenablage einfügen.  
  
 Können Sie kopieren oder Ausschneiden den Inhalt der aktuellen Auswahl mit der [Kopie](../mfc/reference/cricheditctrl-class.md#copy) oder [Ausschneiden](../mfc/reference/cricheditctrl-class.md#cut) Memberfunktion. Sie können auf ähnliche Weise den Inhalt der Zwischenablage in ein rich-Edit-Steuerelement einfügen, mit der [einfügen](../mfc/reference/cricheditctrl-class.md#paste) Memberfunktion. Das Steuerelement fügt das erste verfügbare Format, das er erkennt, d. h., es empfiehlt sich die am beschreibenden Format.  
  
 Um ein bestimmtes Zwischenablageformat einzufügen, können Sie die [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial) Memberfunktion. Diese Funktion ist nützlich für Anwendungen mit einem Inhalte einfügen-Befehl, der dem Benutzer ermöglicht, wählen Sie das Format der Zwischenablage. Sie können die [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste) Member-Funktion, um zu bestimmen, ob ein bestimmtes Format vom Steuerelement erkannt wird.  
  
 Sie können auch `CanPaste` zu bestimmen, ob ein verfügbares Zwischenablageformat von einem rich-Edit-Steuerelement erkannt wird. Diese Funktion eignet sich für die `OnInitMenuPopup` Handler. Eine Anwendung kann aktiviert oder grau, der Befehl "Einfügen", je nachdem, ob das Steuerelement ein verfügbares Format einfügen kann.  
  
 Rich-Edit-Steuerelemente registrieren zwei Zwischenablageformate: Rich-Text-Format und ein Format, das RichEdit-Text und Objekte aufgerufen. Eine Anwendung kann diese Formate registrieren, indem die [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion angeben der **Werte CF_RTF** und **CF_RETEXTOBJ angegeben werden müssen** Werte.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

