---
title: Darstellen von Bildern aus einer Bildliste | Microsoft Docs
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
- CImageList class [MFC], drawing images from
- drawing [MFC], images from image lists
- image lists [MFC], drawing images from
- images [MFC], drawing
ms.assetid: 2f6063fb-1c28-45f8-a333-008c064db11c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deb9a96d5096b489f8e4dcbaf987509d60bd5024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="drawing-images-from-an-image-list"></a>Darstellen von Bildern aus einer Bildliste
Um ein Bild gezeichnet werden soll, verwenden Sie die [Memberfunktion CImageList:: Draw](../mfc/reference/cimagelist-class.md#draw) Memberfunktion. Geben Sie einen Zeiger auf ein Gerätekontextobjekt, den Index des Bilds gezeichnet werden soll, den Speicherort in den Gerätekontext, an dem das Bild gezeichnet werden soll, und eine Gruppe von Flags an, dass das Zeichnungsformat.  
  
 Geben Sie bei der `ILD_TRANSPARENT` Stil **zeichnen** verwendet einen zweistufiger Prozess, ein maskiertes Bild gezeichnet werden soll. Zuerst führt eine logische- und -Vorgang für die Bits des Bilds und das Bit der Maske. Dann führt es eine logische XOR-Operation für die Ergebnisse des ersten Vorgangs und die Hintergrundbits im des Zielgerätekontexts. Dieser Prozess wird transparente Bereiche in das resultierende Image erstellt; bewirkt, dass jedes Bit der Maske weiß das entsprechende Bit in das resultierende Image transparent.  
  
 Sie sollten vor dem Zeichnen eines maskierten Bilds in einem Hintergrundthread Volltonfarbe, verwenden die [SetBkColor](../mfc/reference/cimagelist-class.md#setbkcolor) Memberfunktion versucht, die die Hintergrundfarbe der Bildliste auf dieselbe Farbe als Ziel festgelegt. Entfällt die Notwendigkeit zum Erstellen der transparente Bereiche in der Abbildung und ermöglicht das Festlegen der Farbe **zeichnen** das Abbild auf den Zielgerätekontext, was zu einem beträchtlichen Anstieg Leistung zu kopieren. Um das Bild gezeichnet werden soll, geben Sie die `ILD_NORMAL` Format zuzuweisen, wenn Sie rufen **zeichnen**.  
  
 Sie können die Hintergrundfarbe für eine maskierte Bildliste festlegen ([CImageList](../mfc/reference/cimagelist-class.md)) zu einem beliebigen Zeitpunkt so, dass die It ordnungsgemäß auf jedem ausgefüllten Hintergrund zeichnet. Festlegen der Hintergrundfarbe auf `CLR_NONE` führt dazu, dass Bilder standardmäßig transparent gezeichnet werden. Um die Farbe des Hintergrunds einer Bildliste abzurufen, verwenden Sie die [GetBkColor](../mfc/reference/cimagelist-class.md#getbkcolor) Memberfunktion.  
  
 Die `ILD_BLEND25` und `ILD_BLEND50` Stile mischen des Abbilds mit der Hervorhebungsfarbe des Systems. Diese Formate sind nützlich, wenn Sie ein maskiertes Bild verwenden, um ein Objekt darzustellen, die der Benutzer auswählen kann. Beispielsweise können Sie die `ILD_BLEND50` Stil für das Bild gezeichnet werden soll, wenn der Benutzer sie auswählt.  
  
 Nicht maskierten Bildes in den Kontext mit Ziel Gerät kopiert die **SRCCOPY** auszuführenden Vorgangs. Die Farben in der Abbildung werden unabhängig von die Hintergrundfarbe des Gerätekontexts angezeigt. Die im angegebenen zeichnungsarten **zeichnen** auch haben keinen Einfluss auf die Darstellung eines nicht maskierten Bilds.  
  
 Zusätzlich zu den Draw-Memberfunktion einer anderen Funktion [DrawIndirect](../mfc/reference/cimagelist-class.md#drawindirect), reicht die Möglichkeit, ein Bild zu rendern. `DrawIndirect`akzeptiert, die als Parameter ein [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) Struktur. Diese Struktur kann verwendet werden, um das Rendering des aktuellen Images, einschließlich der Verwendung von rastervorgangscode (ROP) anzupassen. Weitere Informationen zu ROP Codes finden Sie unter [Rastervorgangscode](http://msdn.microsoft.com/library/windows/desktop/dd162892) und [Bitmaps als Pinsel](http://msdn.microsoft.com/library/windows/desktop/dd183378) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

