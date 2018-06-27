---
title: Verwenden einer Bildliste mit einem Grundleisten-Steuerelement | Microsoft Docs
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
ms.openlocfilehash: 1786c89f4ec9cf1c0908dac5d81858d5b2e6b7db
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950705"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>Verwenden einer Bildliste mit einem Grundleisten-Steuerelement
Jedes Band Grundleisten kann unter anderem ein Bild aus einer Bildliste zugeordneten enthalten. Das folgende Verfahren erläutert die notwendigen Schritte zum Anzeigen eines Bilds in einem Grundleisten-Band.  
  
### <a name="to-display-images-in-a-rebar-band"></a>Anzeige von Bildern in einem Grundleisten-band  
  
1.  Fügen Sie eine Bildliste für Ihr Grundleisten-Steuerelement-Objekt, indem Sie einen Aufruf an [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist), die Übergabe eines Zeigers auf eine vorhandene Bildliste.  
  
2.  Ändern der **REBARBANDINFO** -Struktur mit einem Grundleisten-Sperrband ein Bild zuzuweisen:  
  
    -   Legen Sie die *fMask* Member `RBBIM_IMAGE`, mit dem bitweisen OR-Operator nach Bedarf zusätzliche Flags enthalten.  
  
    -   Legen Sie die *iImage* Element der Liste Abbildindex des Bilds angezeigt werden.  
  
3.  Initialisieren Sie alle verbleibenden Datenmember, z. B. die Größe, Text und Handle des enthaltenen untergeordneten Fenster mit den erforderlichen Informationen.  
  
4.  Fügen Sie das neue Band (mit dem Image) mit einem Aufruf von [CReBarCtrl:: InsertBand](../mfc/reference/crebarctrl-class.md#insertband), und übergeben Sie die **REBARBANDINFO** Struktur.  
  
 Im folgende Beispiel wird davon ausgegangen, dass ein vorhandenes Image Listenobjekt mit zwei Bildern an das Grundleisten-Steuerelement-Objekt angefügt wurde (`m_wndReBar`). Ein neues Infoleistenband (definiert durch `rbi`), das das erste Bild enthält, wird mit einem Aufruf von hinzugefügt `InsertBand`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

