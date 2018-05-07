---
title: Formatieren von Absätzen in RichEdit-Steuerelementen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 113d47a88f0de7ddd12f474678705688569ad50d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Formatieren von Absätzen in RichEdit-Steuerelementen
Können Sie Memberfunktionen des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Absätzen und Formatierungsinformationen abzurufen. Absatz Formatierungsattribute einschließen Ausrichtung, Registerkarten, Einzüge und Nummerierung  
  
 Sie können mithilfe von Formatieren von Absätzen Anwenden der [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) Memberfunktion. Verwenden Sie zum Bestimmen der aktuellen für den ausgewählten Text Formatieren von Absätzen der [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) Memberfunktion. Die [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) Struktur wird mit diesen Memberfunktionen verwendet, um Absatzattribute angeben. Eine der wichtigen Member der **PARAFORMAT** ist **DwMask**. In `SetParaFormat`, **DwMask** gibt an, welche Absatzattribute durch Aufrufen der Funktion festgelegt werden. `GetParaFormat` meldet die Attribute aus dem ersten Absatz in der Auswahl. **DwMask** gibt die Attribute, die gesamte Auswahl konsistent sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

