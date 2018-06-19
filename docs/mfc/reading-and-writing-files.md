---
title: Lesen und Schreiben von Dateien | Microsoft Docs
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
ms.openlocfilehash: 102f5f5de591f8a4475232ad8f0f5383c276e5d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347934"
---
# <a name="reading-and-writing-files"></a>Lesen und Schreiben von Dateien
Wenn Sie die Funktionen der C-Laufzeitbibliothek Dateibehandlung verwendet haben, erscheint MFC Lese- und Schreibvorgänge vertraut. Dieser Artikel beschreibt das direkte Lesen aus und Schreiben von direkt an eine `CFile` Objekt. Sie können auch gepuffert Datei-e/a mit der [CArchive](../mfc/reference/carchive-class.md) Klasse.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>Lese-und Schreibberechtigungen für die Datei  
  
1.  Verwenden der **lesen** und **schreiben** Memberfunktionen zum Lesen und Schreiben von Daten in der Datei.  
  
     - oder -   
  
2.  Die `Seek` Memberfunktion ist auch verfügbar, um an einem bestimmten Offset innerhalb der Datei zu verschieben.  
  
 **Lesen** verwendet einen Zeiger auf einen Puffer und die Anzahl der zu lesenden Bytes und gibt die tatsächliche Anzahl von Bytes, die gelesen wurden. Wenn die erforderliche Anzahl von Bytes da Ende der Datei konnte nicht gelesen werden (EOF) erreicht ist, wird die tatsächliche Anzahl der gelesenen Bytes zurückgegeben. Wenn ein Lesefehler auftritt, wird eine Ausnahme ausgelöst. **Schreiben von** ähnelt **lesen**, aber die Anzahl der geschriebenen Bytes nicht zurückgegeben. Wenn ein Schreibfehler auftritt, einschließlich aller Bytes angegeben, aber nicht das Schreiben, wird eine Ausnahme ausgelöst. Wenn Sie eine gültige haben `CFile` -Objekt, können Sie daraus zu lesen oder schreiben, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  Führen Sie sollte normalerweise aus der e/a-Vorgänge innerhalb einer **versuchen**/**catch** Block zur Ausnahmebehandlung. Weitere Informationen finden Sie unter [Ausnahmebehandlung (MFC)](../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)

