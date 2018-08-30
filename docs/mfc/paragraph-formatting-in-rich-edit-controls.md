---
title: Formatieren von Absätzen in RichEdit-Steuerelementen | Microsoft-Dokumentation
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
ms.openlocfilehash: 8258ff95fc91f6f29d424e77be95ce1b44f621ac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215820"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>Formatieren von Absätzen in RichEdit-Steuerelementen
Können Sie Memberfunktionen des rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) zum Formatieren von Absätzen und zum Abrufen von Informationen über die Formatierung. Absatz Formatierungsattribute enthalten Ausrichtung, Registerkarten, Einzügen und Aufzählungszeichen.  
  
 Sie können mithilfe von Formatieren von Absätzen Anwenden der [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat) Member-Funktion. Verwenden Sie zum Bestimmen des aktuellen Absatzes, für den markierten Text Formatieren der [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat) Member-Funktion. Die [ABSATZFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat) Struktur mit dieser Memberfunktionen verwendet, um Absatzattribute anzugeben. Eines der wichtigen Member von **ABSATZFORMAT** ist *DwMask*. In `SetParaFormat`, *DwMask* gibt an, welche Absatzattribute durch Aufrufen der Funktion festgelegt werden sollen. `GetParaFormat` meldet die Attribute des ersten Absatzes in der Auswahl. *DwMask* gibt die Attribute, die in die Auswahl konsistent sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

