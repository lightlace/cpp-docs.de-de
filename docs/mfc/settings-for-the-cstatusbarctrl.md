---
title: Einstellungen für CStatusBarCtrl | Microsoft Docs
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
ms.openlocfilehash: 1eea701c33001ffa3585c2d5847f3056454b7850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380161"
---
# <a name="settings-for-the-cstatusbarctrl"></a>Einstellungen für CStatusBarCtrl
Die Standardposition des eine [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) Statusfenster wird am unteren Rand des übergeordneten Fensters, aber Sie können angeben, die `CCS_TOP` Stil, damit diese am oberen Rand der Clientbereich des übergeordneten Fensters angezeigt.  
  
 Sie können angeben, die **SBARS_SIZEGRIP** Formatvorlage enthalten einen Größenziehpunkt am rechten Ende der `CStatusBarCtrl` Statusfenster. Ein Größenziehpunkt ist vergleichbar mit einem Rahmen; Es ist ein rechteckigen Bereichs, der der Benutzer kann klicken und ziehen Sie zum Ändern der Größe des übergeordneten Fensters.  
  
> [!NOTE]
>  Wenn Sie kombinieren der `CCS_TOP` und **SBARS_SIZEGRIP** Formatvorlagen, die sich ergebende Größenziehpunkt ist nicht funktionsfähig, obwohl das System im Statusfenster zeichnet.  
  
 Die Fensterprozedur für das Statusfenster legt automatisch die anfängliche Größe und Position des Steuerelements. Die Breite entspricht den Clientbereich des übergeordneten Fensters. Die Höhe basiert auf den Metriken der Schriftart, die derzeit dem Statusfenster Gerätekontext ausgewählt ist und die Breite des Fensterrahmens.  
  
 Die Fensterprozedur automatisch die Größe des Fensters der anpasst, wenn er empfängt eine `WM_SIZE` Nachricht. In der Regel, wenn die Größe des übergeordneten Fensters ändert, sendet das übergeordnete Element einer `WM_SIZE` Nachricht im Statusfenster.  
  
 Sie können die minimale Höhe der Zeichnungsbereich einer Statusfenster festlegen, durch den Aufruf [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), die minimale Höhe in Pixel angibt. Der Zeichnungsbereich umfasst keine des Fensterrahmens.  
  
 Die Breite des Rahmens eines Fensters Status abrufen rufen Sie [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders). Diese Memberfunktion umfasst die Zeiger auf ein Array mit drei Elementen, die die Breite des horizontalen Rands vertikalen Rands und dem Rahmen zwischen Rechtecke empfängt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

