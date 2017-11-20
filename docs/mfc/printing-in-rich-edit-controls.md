---
title: Drucken mit RichEdit-Steuerelementen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d93611d66d394d4ed182261d3bba3121464931d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="printing-in-rich-edit-controls"></a>Drucken mit RichEdit-Steuerelementen
Sie können feststellen, ein Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) Rendern die Ausgabe für ein angegebenes Gerät, z. B. ein Drucker. Sie können auch angeben, dass das Ausgabegerät für das ein Rich-Steuerelement Edit seinen Text formatiert.  
  
 Um Teil des Inhalts eines rich-Edit-Steuerelements für ein bestimmtes Gerät zu formatieren, können Sie die [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange) Memberfunktion. Die [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) Struktur verwendet, die mit dieser Funktion gibt den Bereich der Text so formatieren Sie sowie den Gerätekontext (DC) für das Zielgerät.  
  
 Nach der Formatierung von Text für ein Ausgabegerät, können Sie die Ausgabe an das Gerät senden, mit der [DisplayBand](../mfc/reference/cricheditctrl-class.md#displayband) Memberfunktion. Wiederholt mit `FormatRange` und `DisplayBand`, eine Anwendung, die den Inhalt eines rich-Edit-Steuerelements druckt kann banding implementieren. (Banding ist Division der Ausgabe in kleinere Teile zu druckenden.)  
  
 Sie können die [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice) Memberfunktion an das Zielgerät, für die ein Rich--Steuerelement Edit, seinen Text formatiert. Diese Funktion ist nützlich für WYSIWYG (was angezeigt wird, erhalten Sie) formatieren, in dem eine Anwendung Text mit den Standarddrucker Schriftarteigenschaften anstelle des Bildschirms positioniert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

