---
title: Verwenden einer Bildliste | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- lists [MFC], image
- CImageList class [MFC], using
- image lists [MFC]
ms.assetid: e0aed188-a1e6-400e-9f51-033d61c5541f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4321649bf4e8fe0e34fef8fe37b8c96598bef2c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

