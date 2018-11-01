---
title: Bearbeiten von Bildlisten
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], manipulating
- lists [MFC], image
- CImageList class [MFC], manipulating
ms.assetid: 043418f8-077e-4dce-b8bb-2b7b0d7b5156
ms.openlocfilehash: 7ec641f1e7090e27edd367203b430b932ede52a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643767"
---
# <a name="manipulating-image-lists"></a>Bearbeiten von Bildlisten

Die [ersetzen](../mfc/reference/cimagelist-class.md#replace) Memberfunktion ersetzt ein Bild in einer Bildliste ([CImageList](../mfc/reference/cimagelist-class.md)) mit einem neuen Abbild. Diese Funktion ist auch nützlich, wenn die Anzahl der Bilder in einem Image List-Objekt dynamisch erhöht werden muss. Die [SetImageCount](../mfc/reference/cimagelist-class.md#setimagecount) -Funktion ändert dynamisch die Anzahl der Bilder in der Bildliste gespeichert. Wenn Sie die Größe der Liste der Bilder erhöhen, rufen `Replace` zum Hinzufügen von Bildern in das neue Image-Slots. Wenn Sie die Größe der Liste der Bilder verringern, werden die Bilder über die neue Größe freigegeben.

Die [entfernen](../mfc/reference/cimagelist-class.md#remove) Memberfunktion entfernt ein Bild aus einer Bildliste. Die [Kopie](../mfc/reference/cimagelist-class.md#copy) Memberfunktion kopieren oder Bilder in einer Bildliste austauschen kann. Mit dieser Funktion können Sie angeben, ob das Quellimage an den Zielindex kopiert werden sollen, oder die Quelle und Ziel-Images getauscht werden soll.

Um eine neue Bildliste durch Zusammenführen von zwei Bildlisten zu erstellen, verwenden Sie die geeignete Überladung der der [erstellen](../mfc/reference/cimagelist-class.md#create) Member-Funktion. Diese Überladung der `Create` Zusammenführungen, die das erste Bild des vorhandenen Bildes aufgeführt sind, speichern das resultierende Image in ein neues Image List-Objekt. Das neue Image wird erstellt, durch das zweite Bild transparent über das erste zu zeichnen. Die Maske für das neue Image ist das Ergebnis der Ausführung einer logischen OR-Operation für die Bits der Maske für die beiden vorhandenen Images.

Dies wird wiederholt, bis alle Bilder zusammengeführt und das neue Image List-Objekt hinzugefügt.

Sie können die Image-Informationen in ein Archiv schreiben, durch den Aufruf der [schreiben](../mfc/reference/cimagelist-class.md#write) Member-Funktion, und auch wieder durch Aufrufen der [lesen](../mfc/reference/cimagelist-class.md#read) Member-Funktion.

Die [Memberfunktionen GetSafeHandle](../mfc/reference/cimagelist-class.md#getsafehandle), [Anfügen](../mfc/reference/cimagelist-class.md#attach), und [trennen](../mfc/reference/cimagelist-class.md#detach) Member-Funktionen können Sie das Handle der Bildliste hinzugefügt Bearbeiten der `CImageList` Objekt während der [Memberfunktion DeleteImageList](../mfc/reference/cimagelist-class.md#deleteimagelist) Memberfunktion löscht die Liste der Bilder ohne zu zerstören der `CImageList` Objekt.

## <a name="see-also"></a>Siehe auch

[Verwenden von CImageList](../mfc/using-cimagelist.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

