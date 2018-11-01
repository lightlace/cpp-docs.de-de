---
title: Verwenden eines Standardsteuerelements als untergeordnetes Fenster
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 690b48cf50e95265aaf5bdd454e2881b8f5fab3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655129"
---
# <a name="using-a-common-control-as-a-child-window"></a>Verwenden eines Standardsteuerelements als untergeordnetes Fenster

Eines der allgemeinen Windows-Steuerelemente kann als untergeordnetes Fenster von einem anderen Fenster verwendet werden. Das folgende Verfahren beschreibt ein allgemeines Steuerelement dynamisch zu erstellen und mit dem Sie arbeiten.

### <a name="to-use-a-common-control-as-a-child-window"></a>Verwenden ein Standardsteuerelements als untergeordnetes Fenster

1. Definieren Sie das Steuerelement in der entsprechenden Klasse oder der Handler.

1. Verwenden Sie die Überschreibung von der [CWnd:: Create](../mfc/reference/cwnd-class.md#create) Methode, um das Windows-Steuerelement zu erstellen.

1. Nachdem das Steuerelement erstellt wurde (wie früher als die `OnCreate` Handler Wenn Sie eine Unterklasse des Steuerelements), können Sie das Steuerelement über seine Memberfunktionen ändern. Finden Sie in den Beschreibungen der einzelnen Steuerelemente am [Steuerelemente](../mfc/controls-mfc.md) Weitere Informationen zu Methoden.

1. Wenn Sie mit dem Steuerelement fertig sind, verwenden Sie [CWnd:: DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) zerstört das Steuerelement.

## <a name="see-also"></a>Siehe auch

[Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

