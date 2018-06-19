---
title: Verwenden einer Bildliste | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5722a2ef8c4e93e4996ee243b3c01b6dd6aeca78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381604"
---
# <a name="using-an-image-list"></a>Verwenden einer Bildliste
Typische Verwendung einer Bildliste entspricht dem folgenden Muster:  
  
-   Erstellen einer [CImageList](../mfc/reference/cimagelist-class.md) Objekt, und rufen Sie eine der Überladungen der seine [erstellen](../mfc/reference/cimagelist-class.md#create) Funktion zum Erstellen einer Bildliste, und fügen Sie es auf die `CImageList` Objekt.  
  
-   Wenn Sie Bilder hinzufügen, haben nicht Sie beim Erstellen der Bildliste Hinzufügen von Bildern auf die Bildliste durch Aufrufen der [hinzufügen](../mfc/reference/cimagelist-class.md#add) oder [lesen](../mfc/reference/cimagelist-class.md#read) Memberfunktion.  
  
-   Durch Aufrufen der entsprechenden Memberfunktion dieses Steuerelements die Bildliste einem Steuerelement zuordnen, oder Zeichnen Sie die Bildliste selbst unter Verwendung der Bildliste [zeichnen](../mfc/reference/cimagelist-class.md#draw) Memberfunktion.  
  
-   Möglicherweise können Sie Benutzer, ziehen ein Bild, verwenden die Bildliste integrierte Unterstützung für ziehen.  
  
> [!NOTE]
>  Wenn die Bildliste mit erstellt wurde die **neue** -Operator, müssen Sie zerstören der `CImageList` Objekt, wenn Sie damit fertig sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

