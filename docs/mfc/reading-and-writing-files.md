---
title: Lesen und Schreiben von Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0fd41c085b9498d3f1ebb76378a83cce464142a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404071"
---
# <a name="reading-and-writing-files"></a>Lesen und Schreiben von Dateien

Wenn Sie die Funktionen der C-Laufzeitbibliothek zur Behandlung von Datei verwendet haben, erscheint MFC Lese- und Schreibvorgänge vertraut. Dieser Artikel beschreibt das direkte Lesen aus und Schreiben von direkt an eine `CFile` Objekt. Sie können auch gepufferte Datei-e/a mit der [CArchive](../mfc/reference/carchive-class.md) Klasse.

#### <a name="to-read-from-and-write-to-the-file"></a>Lese-und Schreibberechtigungen für die Datei

1. Verwenden der `Read` und `Write` Memberfunktionen zum Lesen und Schreiben von Daten in der Datei.

     - oder - 

1. Die `Seek` Memberfunktion finden Sie auch für das Verschieben in einem bestimmten Offset in der Datei.

`Read` verwendet einen Zeiger auf einen Puffer und die Anzahl der zu lesenden Bytes und gibt die tatsächliche Anzahl von Bytes, die gelesen wurden. Wenn die erforderliche Anzahl von Bytes nicht da-Dateiende gelesen werden konnte (EOF) erreicht ist, wird die tatsächliche Anzahl der gelesenen Bytes zurückgegeben. Wenn ein Lesefehler auftritt, wird eine Ausnahme ausgelöst. `Write` ist vergleichbar mit `Read`, aber nicht die Anzahl der geschriebenen Bytes zurückgegeben. Wenn ein Schreibfehler auftritt, einschließlich aller Bytes angegeben, aber nicht das Schreiben, wird eine Ausnahme ausgelöst. Wenn Sie einen gültigen haben `CFile` -Objekt, können Sie daraus zu lesen oder schreiben, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
>  Sollte normalerweise ein Vorabfüllen e/a-Vorgänge innerhalb einer **versuchen**/**catch** Block zur Ausnahmebehandlung. Weitere Informationen finden Sie unter [Ausnahmebehandlung (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[Dateien](../mfc/files-in-mfc.md)

