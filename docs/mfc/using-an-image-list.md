---
title: Verwenden einer Bildliste
ms.date: 11/04/2016
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
ms.openlocfilehash: cb95de134939e1b06e2a8b827424c986f8c48ef3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180465"
---
# <a name="using-an-image-list"></a>Verwenden einer Bildliste

Typische Verwendung einer Bildliste folgt das folgenden Muster:

- Erstellen einer [CImageList](../mfc/reference/cimagelist-class.md) Objekt aus, und rufen Sie eine der Überladungen der seine [erstellen](../mfc/reference/cimagelist-class.md#create) -Funktion zum Erstellen eine Bildliste aus, und fügen Sie ihn auf die `CImageList` Objekt.

- Wenn Sie Images beim Erstellen der Bildliste hinzugefügt haben, können Sie Bilder der Bildliste hinzufügen, durch den Aufruf der [hinzufügen](../mfc/reference/cimagelist-class.md#add) oder [lesen](../mfc/reference/cimagelist-class.md#read) Member-Funktion.

- Ordnen Sie die Bildliste mit einem Steuerelement durch Aufrufen der entsprechenden Member-Funktion des Steuerelements, oder Zeichnen Sie aus der Bildliste selbst unter Verwendung der Bildliste [zeichnen](../mfc/reference/cimagelist-class.md#draw) Member-Funktion.

- Vielleicht können Sie Benutzer ein Bild aus der Bildliste integrierte Unterstützung für das Ziehen von ziehen.

> [!NOTE]
>  Wenn die Bildliste mit erstellt wurde die **neue** -Operator, müssen Sie löschen die `CImageList` Objekt, wenn Sie damit fertig sind.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)
