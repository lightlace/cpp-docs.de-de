---
title: Einstellungen für CStatusBarCtrl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2411659e6ae33fe9ce81d508d3e7c206b1e5b113
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440029"
---
# <a name="settings-for-the-cstatusbarctrl"></a>Einstellungen für CStatusBarCtrl

Die Standardposition des eine [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) Statusfenster wird am unteren Rand des übergeordneten Fensters, aber Sie können angeben, den Stil CCS_TOP-Format so, dass sie am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt werden.

Sie können angeben, das SBARS_SIZEGRIP-Format enthält einen Größenziehpunkt am rechten Ende der `CStatusBarCtrl` Statusfenster. Ein Größenziehpunkt ist vergleichbar mit einem Rahmen; Es ist eines rechteckigen Bereichs, das der Benutzer kann klicken und ziehen Sie zum Ändern der Größe des übergeordneten Fensters.

> [!NOTE]
>  Wenn Sie die Stile CCS_TOP-Format und SBARS_SIZEGRIP kombinieren, ist der resultierende Größenziehpunkt nicht funktionsfähig, obwohl das System im Fenster zeichnet.

Die Fensterprozedur für das Statusfenster legt automatisch fest, die ursprüngliche Größe und Position des Steuerelements. Die Breite ist identisch mit der Clientbereich des übergeordneten Fensters. Die Höhe basiert auf die Metriken für die Schriftart, die das Statusfenster Gerätekontext derzeit ausgewählt ist und die Breite des Fensterrahmens.

Die Fensterprozedur wird die Größe des Fensters der automatisch angepasst, wenn sie eine WM_SIZE-Meldung empfängt. Wenn die Größe des übergeordneten Fensters ändert, sendet das übergeordnete Element in der Regel eine WM_SIZE-Meldung im Statusfenster.

Sie können die minimale Höhe der Zeichnungsbereich einer Statusfenster festlegen, durch den Aufruf [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), die minimale Höhe in Pixel angibt. Zeichenbereich umfasst keine des Fensterrahmens.

Rufen Sie die Breite des Rahmens eines Fensters Status durch den Aufruf [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Diese Memberfunktion schließt den Zeiger auf ein Array mit drei Elementen, die die Breite des horizontalen Rands den vertikalen Rahmen und der Rahmen zwischen den Rechtecken empfängt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

