---
title: Verwenden einer Bildliste mit einem Grundleisten-Steuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ff524f1f29e4db2ac5bb4628064583f0fe7583e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372365"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Verwenden einer Bildliste mit einem Grundleisten-Steuerelement

Jede Infoleistenband kann unter anderem ein Bild aus einer Liste zugeordnete Bild enthalten. Das folgende Verfahren erläutert die notwendigen Schritte zum Anzeigen eines Bilds in ein Infoleistenband.

### <a name="to-display-images-in-a-rebar-band"></a>Zum Anzeigen von Bildern in ein Infoleistenband

1. Fügen Sie eine Bildliste an das Grundleisten-Steuerelement-Objekt, von einem Aufruf an [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), Übergabe eines Zeigers an eine vorhandene Image-Liste.

1. Ändern der **REBARBANDINFO** Struktur, ein Bild ein Infoleistenband zuzuweisen:

   - Legen Sie die *fMask* Member `RBBIM_IMAGE`, mit dem bitweisen OR-Operator nach Bedarf zusätzliche Flags sollen.

   - Legen Sie die *iImage* Element der Liste Bildindex des Images, die angezeigt werden.

1. Initialisieren Sie alle verbleibenden Datenmember, z. B. die Größe, Text und Handle des enthaltenen untergeordneten Fensters mit den notwendigen Informationen.

1. Fügen Sie das neue Band (mit dem Bild) mit einem Aufruf von [CReBarCtrl:: InsertBand](../mfc/reference/crebarctrl-class.md#insertband), und übergeben Sie die **REBARBANDINFO** Struktur.

Im folgende Beispiel wird davon ausgegangen, dass ein vorhandene Image List-Objekt mit zwei Bildern an das Grundleisten-Steuerelement-Objekt angefügt wurde (`m_wndReBar`). Ein neues Infoleistenband (definiert durch `rbi`), der das erste Bild enthält, wurde durch einen Aufruf von `InsertBand`:

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

