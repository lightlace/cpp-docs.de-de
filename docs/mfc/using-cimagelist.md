---
title: Verwenden von CImageList | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CImageList
dev_langs:
- C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ebfcb8fbacd3c464fc3697fc15bad385c1547d4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420655"
---
# <a name="using-cimagelist"></a>Verwenden von CImageList

Eine Bildliste, dargestellt durch die Klasse [CImageList](../mfc/reference/cimagelist-class.md), ist eine Auflistung von gleichen Bilder, von denen jeder über seinen Index verwiesen werden kann. Bilderliste für das werden verwendet, um große Mengen von Symbolen oder Bitmaps effizient zu verwalten. Bild von Listen sind Sie selbst keine Steuerelemente, da es keine Windows; Sie werden jedoch verschiedene Typen von Steuerelementen, einschließlich der Listensteuerelemente verwendet ([CListCtrl](../mfc/reference/clistctrl-class.md)), Struktursteuerelemente ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)), und Registerkarten-Steuerelementen ([CTabCtrl](../mfc/reference/ctabctrl-class.md)).

Alle Abbilder in einer Bildliste sind in eine einzelne, große Bitmap im Bildschirm-Device-Format enthalten. Eine Bildliste kann auch eine monochrome Bitmap enthalten, die zum Zeichnen von Bildern transparent Masken (Symbolart) enthält. `CImageList` enthält die Member-Funktionen, mit denen Sie zum Zeichnen von Bildern, erstellen und Zerstören von Bildlisten, hinzufügen und Entfernen von Bildern, Ersetzen von Bildern, Zusammenfügen von Bildern, und ziehen Images.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Bildlistenarten](../mfc/types-of-image-lists.md)

- [Verwenden einer Bildliste](../mfc/using-an-image-list.md)

- [Bearbeiten von Bildlisten](../mfc/manipulating-image-lists.md)

- [Darstellen von Bildern aus einer Bildliste](../mfc/drawing-images-from-an-image-list.md)

- [Overlaymasken in Bildlisten](../mfc/image-overlays-in-image-lists.md)

- [Herausziehen von Bildern aus einer Bildliste](../mfc/dragging-images-from-an-image-list.md)

- [Bildinformationen in Bildlisten](../mfc/image-information-in-image-lists.md)

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)

