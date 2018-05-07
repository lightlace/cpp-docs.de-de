---
title: Umgehen des Serialisierungsmechanismus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a45779034534ce87bd6bd4f55dfda4985a36f01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bypassing-the-serialization-mechanism"></a>Umgehen des Serialisierungsmechanismus
Wie Sie gesehen haben, bietet das Framework eine Standardmethode zum Lesen und Schreiben von Daten in und aus Dateien. Über ein Archivobjekt serialisieren passt die Anforderungen eine hervorragende vieler Anwendungen. Eine solche Anwendung liest eine Datei vollständig in den Arbeitsspeicher, ermöglicht dem Benutzer die Datei zu aktualisieren und dann die aktualisierte Version erneut auf den Datenträger schreibt.  
  
 Allerdings einige Anwendungen verarbeiten Daten sehr unterschiedlich, und für diese Anwendungen nicht über ein Archiv Serialisierung geeignet ist. Beispiele umfassen Datenbankprogramme, Programme, die nur Teile großer Dateien zu bearbeiten, Programme, die nur-Text-Dateien zu schreiben und Programme, die Datendateien gemeinsam nutzen.  
  
 In diesen Fällen können Sie überschreiben die [Serialize](../mfc/reference/cobject-class.md#serialize) -Funktion in eine andere Möglichkeit, zu vermitteln, Dateiaktionen über einen [CFile](../mfc/reference/cfile-class.md) Objekt anstelle eines [CArchive](../mfc/reference/carchive-class.md) Objekt.  
  
 Können Sie die **öffnen**, **lesen**, **schreiben**, **schließen**, und `Seek` Memberfunktionen der Klasse `CFile` öffnen eine Datei , bewegen Sie den Dateizeiger (seek) zu einem bestimmten Zeitpunkt in der Datei liest einen Datensatz (eine angegebene Anzahl von Bytes) an diesem Punkt, den Datensatz aktualisieren zu lassen klicken Sie dann zu suchen, die denselben Zeitpunkt erneut aus und schreiben, die der Datensatz in die Datei zu sichern. Das Framework wird die Datei für Sie geöffnet, und können Sie die `GetFile` Memberfunktion der Klasse `CArchive` um einen Zeiger auf die `CFile` Objekt. Für anspruchsvollere, flexible verwenden, können Sie überschreiben die [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) und [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) Memberfunktionen der Klasse `CWinApp`. Weitere Informationen finden Sie in der Klasse [CFile](../mfc/reference/cfile-class.md) in der *MFC-Referenz*.  
  
 In diesem Szenario die `Serialize` Außerkraftsetzung wird keine Aktion ausgeführt werden, es sei denn, Sie z. B., damit diese lesen und Schreiben eines Datei Headers an, um es auf dem neuesten Stand zu halten, wenn das Dokument geschlossen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

