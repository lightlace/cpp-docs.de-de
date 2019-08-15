---
title: Anpassen der Darstellung des Header&#39;Elements
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 6ce676695d717fcc5d418fe4ed5df91b4f9bca95
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508721"
---
# <a name="customizing-the-header-item39s-appearance"></a>Anpassen der Darstellung des Header&#39;Elements

Wenn Sie den *dwstyle* -Parameter festlegen, wenn Sie erstmalig ein Header Steuerelement erstellen ([CHeaderCtrl:: Create](../mfc/reference/cheaderctrl-class.md#create)), können Sie die Darstellung und das Verhalten von Header Elementen oder dem Header Steuerelement selbst definieren.

Im folgenden finden Sie eine Stichprobe der Stile, die Sie festlegen können, und deren Zweck:

- Verwenden Sie den **HDS_BUTTONS** -Stil, damit ein Header Element wie ein PUSHBUTTON aussieht.

   Verwenden Sie dieses Format, wenn Sie Aktionen als Reaktion auf Mausklicks für ein Header Element ausführen möchten, z. b. das Sortieren von Daten nach einer bestimmten Spalte, wie dies in Microsoft Outlook der Fall ist.

- Verwenden Sie den **HDS_HOTTRACK** -Stil, um dem Header Elemente eine "Hot Tracking"-Darstellung zu übergeben, wenn der Mauszeiger darüber bewegt wird.

   Bei der aktiven Nachverfolgung wird eine 3D-Gliederung angezeigt, während der Zeiger über ein Element in einem andernfalls flachen Balken verläuft.

- Um anzugeben, dass das Header Steuerelement ausgeblendet werden soll, verwenden Sie den **HDS_HIDDEN** -Stil.

   Der **HDS_HIDDEN** -Stil gibt an, dass das Header Steuerelement als Datencontainer und nicht als visuelles Steuerelement verwendet werden soll. Dieser Stil verbirgt das Steuerelement nicht automatisch, sondern wirkt sich stattdessen auf das Verhalten `CHeaderCtrl::Layout`von aus. Der im *CY* -Member der `WINDOWPOS` -Struktur zurückgegebene Wert ist 0 (null), um anzugeben, dass das Steuerelement für den Benutzer nicht sichtbar sein soll.

Weitere Informationen zu diesen Eigenschaften finden Sie unter [Items](/windows/win32/Controls/header-controls) in the Windows SDK. Weitere Informationen zum Hinzufügen von Elementen zu einem Header Steuerelement finden [Sie unter Hinzufügen von Elementen zum Header Steuer](../mfc/adding-items-to-the-header-control.md)Element.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
