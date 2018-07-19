---
title: Einstellungen für das Statussteuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26afdcb58a64f2d2042596349acc4496aa530468
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380008"
---
# <a name="settings-for-the-progress-control"></a>Einstellungen für das Statussteuerelement
Die grundlegenden Einstellungen für das Statussteuerelement ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) sind der Bereich und die aktuelle Position. Der Bereich stellt die gesamte Dauer des Vorgangs dar. Die aktuelle Position darstellt, den Status, den Ihre Anwendung, bis zum Abschließen des Vorgangs erzielt hat. Alle Änderungen an den Bereich oder die Position dazu führen, dass das Statussteuerelement selbst neu zeichnet.  
  
 Standardmäßig wird der Bereich festgelegt, 0 - 100, und die ursprüngliche Position auf 0 festgelegt ist. Verwenden Sie zum Abrufen der aktuellen Einstellungen des aktivierungsbereichs für das Statussteuerelement der [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) Memberfunktion. Verwenden Sie zum Ändern des Bereichs der [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) Memberfunktion.  
  
 Verwenden Sie zum Festlegen der Position [Memberfunktion SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Verwenden Sie zum Abrufen der aktuellen Position ohne Angabe eines neuen Werts [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Sie möchten z. B. einfach eine Abfrage in den Status des laufenden Vorgangs.  
  
 Um die aktuelle Position des Statussteuerelements durchzuführen, verwenden Sie [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Verwenden Sie zum Festlegen der Größe der einzelnen Schritte [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

