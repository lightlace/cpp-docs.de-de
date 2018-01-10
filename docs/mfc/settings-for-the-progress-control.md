---
title: "Einstellungen für das Statussteuerelement | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ad62f3a60c8fe4fcd7efdde7f69f5c5e9450d14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-progress-control"></a>Einstellungen für das Statussteuerelement
Die grundlegenden Einstellungen für das Statussteuerelement ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) sind der Bereich und die aktuelle Position. Der Bereich stellt die gesamte Dauer des Vorgangs dar. Die aktuelle Position darstellt, den Status, den Ihre Anwendung, bis zum Abschließen des Vorgangs erzielt hat. Alle Änderungen an den Bereich oder die Position dazu führen, dass das Statussteuerelement selbst neu zeichnet.  
  
 Standardmäßig wird der Bereich festgelegt, 0 - 100, und die ursprüngliche Position auf 0 festgelegt ist. Verwenden Sie zum Abrufen der aktuellen Einstellungen des aktivierungsbereichs für das Statussteuerelement der [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) Memberfunktion. Verwenden Sie zum Ändern des Bereichs der [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) Memberfunktion.  
  
 Verwenden Sie zum Festlegen der Position [Memberfunktion SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Verwenden Sie zum Abrufen der aktuellen Position ohne Angabe eines neuen Werts [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Sie möchten z. B. einfach eine Abfrage in den Status des laufenden Vorgangs.  
  
 Um die aktuelle Position des Statussteuerelements durchzuführen, verwenden Sie [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Verwenden Sie zum Festlegen der Größe der einzelnen Schritte [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CProgressCtrl](../mfc/using-cprogressctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

