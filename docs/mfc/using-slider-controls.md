---
title: Verwenden von Schieberegler-Steuerelemente | Microsoft-Dokumentation
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
ms.openlocfilehash: d0496a15b289ec055fd2706975603f25cef13938
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388835"
---
# <a name="using-slider-controls"></a>Verwenden von Schieberegler-Steuerelementen

Typische Verwendung des Schieberegler-Steuerelements basiert auf dem folgenden Muster:

- Das Steuerelement wird erstellt. Wenn das Steuerelement in einer Dialogfeldvorlage angegeben wird, erfolgt die Erstellung automatisch, wenn das Dialogfeld erstellt wird. (Sollten Ihnen eine [CSliderCtrl](../mfc/reference/csliderctrl-class.md) Member in der Dialogfeldklasse, die das Schieberegler-Steuerelement entspricht.) Alternativ können Sie die [erstellen](../mfc/reference/csliderctrl-class.md#create) Member-Funktion, um das Steuerelement als untergeordnetes Fenster von einem beliebigen Fenster zu erstellen.

- Rufen Sie die verschiedenen Satz Memberfunktionen, um Werte für das Steuerelement festzulegen. Änderungen, die Sie vornehmen können, enthalten die minimalen und maximalen Positionen für den Schieberegler festlegen, Teilstriche zu zeichnen, einen Auswahlbereich festlegen und Neupositionieren von den Schieberegler. Für Steuerelemente in einem Dialogfeld, ist ein guter Zeitpunkt, zu diesem Zweck die im Dialogfeld [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) Funktion.

- Während der Benutzer mit dem Steuerelement interagiert, sendet er die verschiedenen Benachrichtigungen. Sie können den Wert des Schiebereglers aus dem Steuerelement extrahieren, durch den Aufruf der [GetPos](../mfc/reference/csliderctrl-class.md#getpos) Member-Funktion.

- Wenn Sie mit dem Steuerelement fertig sind, müssen Sie sicherstellen, dass es ordnungsgemäß zerstört wird. Das Schieberegler-Steuerelement in einem Dialogfeld, ist es und die `CSliderCtrl` Objekt wird automatisch zerstört. Wenn nicht der Fall, Sie sicherstellen, dass sowohl das Steuerelement müssen und die `CSliderCtrl` Objekt ordnungsgemäß zerstört werden.

## <a name="see-also"></a>Siehe auch

[Verwenden von CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

