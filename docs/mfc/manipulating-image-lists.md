---
title: Bearbeiten von Bildlisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1eeccfa5245c6395e530859eb91c7f9a5c01335e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930370"
---
# <a name="manipulating-image-lists"></a>Bearbeiten von Bildlisten
Die [ersetzen](../mfc/reference/cimagelist-class.md#replace) Memberfunktion ersetzt ein Bild in einer Bildliste ([CImageList](../mfc/reference/cimagelist-class.md)) durch ein neues Image. Diese Funktion ist auch nützlich, wenn Sie die Anzahl von Bildern in ein Listenobjekt Image dynamisch zu erhöhen. Die [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) Funktion dynamisch ändert die Anzahl von Images, die in der Bildliste gespeichert. Wenn Sie die Bildliste vergrößern, rufen Sie `Replace` , um das neue Image Slots Bilder hinzuzufügen. Wenn Sie die Bildliste verkleinern, werden die Bilder über die neue Größe hinaus freigegeben.  
  
 Die [entfernen](../mfc/reference/cimagelist-class.md#remove) Memberfunktion entfernt ein Bild aus einer Bildliste. Die [Kopie](../mfc/reference/cimagelist-class.md#copy) Memberfunktion kopieren oder Bilder innerhalb einer Bildliste austauschen kann. Mit dieser Funktion können Sie angeben, ob Quellbilds auf Zielindex kopiert werden sollen, oder die Quell- und Zielschemas Bilder ausgetauscht werden sollen.  
  
 Um eine neue Bildliste durch zwei Bilderliste für das Zusammenführen zu erstellen, verwenden Sie die entsprechende Überladung der der [erstellen](../mfc/reference/cimagelist-class.md#create) Memberfunktion. Diese Überladung der `Create` das erste Bild, der das vorhandene Bild aufgelistet sind, speichern das resultierende Bild in einem neuen Image Listenobjekt Zusammenführungen. Das neue Bild wird erstellt, indem das zweite Bild transparent über das erste zu zeichnen. Die Maske für das neue Image ist das Ergebnis der Ausführung einer logischen OR-Operation für die Bits der Masken für die beiden vorhandenen Images.  
  
 Dies wird wiederholt, bis alle Bilder zusammengeführt und das neue Image Listenobjekt hinzugefügt.  
  
 Sie können ein Archiv die Image-Informationen schreiben, durch Aufrufen der [schreiben](../mfc/reference/cimagelist-class.md#write) Memberfunktion und lesen, die es wieder durch Aufrufen der [lesen](../mfc/reference/cimagelist-class.md#read) Memberfunktion.  
  
 Die [Memberfunktionen GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [Anfügen](../mfc/reference/cimagelist-class.md#attach), und [trennen](../mfc/reference/cimagelist-class.md#detach) Memberfunktionen können Sie das Handle für die Bildliste angefügt Bearbeiten der `CImageList` -Objekt, während die [Memberfunktion DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) Memberfunktion löscht die Bildliste, ohne Sie zu zerstören der `CImageList` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

