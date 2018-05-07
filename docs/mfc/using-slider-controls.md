---
title: Schieberegler-Steuerelemente mit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9180d792f38652b22f430e497ef0e42dc54f6d73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-slider-controls"></a>Verwenden von Schieberegler-Steuerelementen
Typische Verwendung des Schieberegler-Steuerelements entspricht dem folgenden Muster:  
  
-   Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sie müssen eine [CSliderCtrl](../mfc/reference/csliderctrl-class.md) Member in der Dialogfeldklasse, die das Schieberegler-Steuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/csliderctrl-class.md#create) Memberfunktion beim Erstellen des Steuerelements als untergeordnetes Fenster von einem beliebigen Fenster.  
  
-   Rufen Sie die verschiedenen Satz Memberfunktionen können Sie Werte für das Steuerelement festlegen. Änderungen, die Sie vornehmen können, gehören das Festlegen der minimalen und maximalen Positionen für den Schieberegler, Teilstriche gezeichnet, einen Auswahlbereich festlegen, und Neupositionieren des Schiebereglers. Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, zu diesem Zweck im Dialogfeld [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.  
  
-   Wie der Benutzer mit dem Steuerelement interagiert, sendet er verschiedene benachrichtigungsmeldungen. Sie können das Schiebereglerwert aus dem Steuerelement extrahieren, durch Aufrufen der [GetPos](../mfc/reference/csliderctrl-class.md#getpos) Memberfunktion.  
  
-   Wenn Sie mit dem Steuerelement fertig sind, müssen Sie sicherstellen, dass es ordnungsgemäß zerstört wird. Wenn das Schieberegler-Steuerelement in einem Dialogfeld ist es und `CSliderCtrl` Objekt wird automatisch zerstört werden. Wenn nicht der Fall, Sie sicherstellen, dass sowohl im Steuerelement müssen und dem `CSliderCtrl` Objekt ordnungsgemäß zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

