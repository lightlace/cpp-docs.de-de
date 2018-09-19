---
title: Drucken mit RichEdit-Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 882ed020b37ec60c072c8983c61bbe564bb74b04
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217687"
---
# <a name="printing-in-rich-edit-controls"></a>Drucken mit RichEdit-Steuerelementen
Sie können feststellen, eine Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) als Ausgabe für ein bestimmtes Gerät, z. B. ein Drucker zu rendern. Sie können auch angeben, dass das Ausgabegerät, die für das ein Rich-Steuerelement Edit den Text formatiert.  
  
 Um die Inhalte eines rich-Edit-Steuerelements für ein bestimmtes Gerät zu formatieren, können Sie die [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) Member-Funktion. Die [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange) Struktur, die diese Funktion gibt den Bereich von Text zu formatieren sowie den Gerätekontext (DC) für das Zielgerät.  
  
 Nach der Formatierung von Text für ein Ausgabegerät, können Sie die Ausgabe an das Gerät senden, mit der [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) Member-Funktion. Wiederholt mit `FormatRange` und `DisplayBand`, eine Anwendung, die den Inhalt eines rich-Edit-Steuerelements druckt kann Bereiche implementieren. (Bereiche ist die Aufteilung der Ausgabe in kleinere Teile zu druckzwecken zu.)  
  
 Sie können die [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) Member-Funktion zum Festlegen des Zielgeräts für die ein Rich--Steuerelement Edit dessen Text formatiert. Diese Funktion ist nützlich für die WYSIWYG-(was angezeigt wird, was Sie erhalten) formatieren, in dem eine Anwendung des Bildschirms den Standarddrucker Schriftarteigenschaften anstelle von Text positioniert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

