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
ms.openlocfilehash: 9252e08fe672f111dcf2b289b1b12891022a318d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931086"
---
# <a name="bypassing-the-serialization-mechanism"></a>Umgehen des Serialisierungsmechanismus
Wie Sie gesehen haben, bietet das Framework eine Standardmethode zum Lesen und Schreiben von Daten in und aus Dateien. Über ein Archivobjekt serialisieren passt die Anforderungen eine hervorragende vieler Anwendungen. Eine solche Anwendung liest eine Datei vollständig in den Arbeitsspeicher, ermöglicht dem Benutzer die Datei zu aktualisieren und dann die aktualisierte Version erneut auf den Datenträger schreibt.  
  
 Allerdings einige Anwendungen verarbeiten Daten sehr unterschiedlich, und für diese Anwendungen nicht über ein Archiv Serialisierung geeignet ist. Beispiele umfassen Datenbankprogramme, Programme, die nur Teile großer Dateien zu bearbeiten, Programme, die nur-Text-Dateien zu schreiben und Programme, die Datendateien gemeinsam nutzen.  
  
 In diesen Fällen können Sie überschreiben die [Serialize](../mfc/reference/cobject-class.md#serialize) -Funktion in eine andere Möglichkeit, zu vermitteln, Dateiaktionen über einen [CFile](../mfc/reference/cfile-class.md) Objekt anstelle eines [CArchive](../mfc/reference/carchive-class.md) Objekt.  
  
 Können Sie die `Open`, `Read`, `Write`, `Close`, und `Seek` Memberfunktionen der Klasse `CFile` um eine Datei zu öffnen, verschieben Sie den Dateizeiger (seek) zu einem bestimmten Zeitpunkt in der Datei ein Datensatz (eine angegebene Anzahl von Bytes lesen ) an diesem Punkt kann der Benutzer den Datensatz aktualisieren und dann erneut mit demselben Zeitpunkt seek und des Datensatzes zurück in die Datei schreiben. Das Framework wird die Datei für Sie geöffnet, und können Sie die `GetFile` Memberfunktion der Klasse `CArchive` um einen Zeiger auf die `CFile` Objekt. Für anspruchsvollere, flexible verwenden, können Sie überschreiben die [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) und [OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument) Memberfunktionen der Klasse `CWinApp`. Weitere Informationen finden Sie in der Klasse [CFile](../mfc/reference/cfile-class.md) in der *MFC-Referenz*.  
  
 In diesem Szenario die `Serialize` Außerkraftsetzung wird keine Aktion ausgeführt werden, es sei denn, Sie z. B., damit diese lesen und Schreiben eines Datei Headers an, um es auf dem neuesten Stand zu halten, wenn das Dokument geschlossen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

