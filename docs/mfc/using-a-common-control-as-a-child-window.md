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
ms.openlocfilehash: 827690f273852dee8f9461aa9af51f1cf7f4ce6e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180569"
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
