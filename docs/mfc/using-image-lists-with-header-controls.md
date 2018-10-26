---
title: Verwenden von Bildlisten in Headersteuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], image lists
- CHeaderCtrl class [MFC], image lists
- image lists [MFC], header controls
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b12f3ff78f88029067d3b77296979a173dad494d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079648"
---
# <a name="using-image-lists-with-header-controls"></a>Verwenden von Bildlisten in Headersteuerelementen

Header-Elemente haben die Möglichkeit, ein Bild in einem Headerelement anzuzeigen. Dieses Image in einer Liste zugeordnete Bild gespeichert ist 16 x 16 Pixel und die gleichen Eigenschaften wie die Symbol-Images, die in einem Listenansicht-Steuerelement verwendet wurde. Um dieses Verhalten wurde erfolgreich zu implementieren, Sie müssen zuerst erstellen und initialisieren die Bildliste, ordnen Sie die Liste das Kopfzeilen-Steuerelement, und ändern Sie die Attribute des Headerelements, das das Bild angezeigt wird.

Das folgende Verfahren illustriert die Details, die mithilfe eines Zeigers auf ein Headersteuerelement (`m_pHdrCtrl`) und einen Zeiger auf eine Bildliste (`m_pHdrImages`).

### <a name="to-display-an-image-in-a-header-item"></a>Um ein Bild in einem Headerelement anzuzeigen.

1. Erstellen Sie eine neue Bildliste (oder verwenden Sie ein vorhandene Image List-Objekt) mit der [CImageList](../mfc/reference/cimagelist-class.md) -Konstruktor, den resultierenden Zeiger speichern.

1. Initialisieren Sie das neue Image List-Objekt durch Aufrufen [CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Der folgende Code ist ein Beispiel für diesen Aufruf.

   [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_1.cpp)]

1. Hinzufügen von Bildern für jedes Headerelement. Der folgende Code fügt zwei vordefinierte Images.

   [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_2.cpp)]

1. Ordnen Sie die Bildliste mit dem Kopfzeilen-Steuerelement mit einem Aufruf von [:: SetImageList](../mfc/reference/cheaderctrl-class.md#setimagelist).

1. Ändern Sie die Headerelement, um ein Bild aus der Liste zugeordnete Bild anzuzeigen. Im folgende Beispiel weist der ersten Abbildung aus `m_phdrImages`, um das erste Headerelement mit `m_pHdrCtrl`.

   [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/cpp/using-image-lists-with-header-controls_3.cpp)]

Ausführliche Informationen zu den Parameterwerten verwendet, finden Sie in der entsprechenden [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md).

> [!NOTE]
>  Es ist möglich, mehrere Steuerelemente, die über dieselbe Bildliste haben. Z. B. in einem standard-Listenansicht-Steuerelement möglicherweise eine Bildliste (von 16 x 16-Pixel-Images) verwendet werden, indem sowohl der Ansicht kleine Symbole von einem Listenansicht-Steuerelement und die Headerelemente des Listenansicht-Steuerelement.

## <a name="see-also"></a>Siehe auch

[Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)

