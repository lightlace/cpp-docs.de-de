---
title: Bereinigen von Dokumenten und Ansichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dfe54c13db6f44bc70289380ae5f50d99c3722b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cleaning-up-documents-and-views"></a>Bereinigen von Dokumenten und Ansichten
Wenn ein Dokument geschlossen wird, ruft das Framework zuerst die [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) Memberfunktion. Wenn Sie im Verlauf des Vorgangs für das Dokument, Arbeitsspeicher, der auf dem Heap zugeordnet `DeleteContents` ist der beste Ort, um ihn freizugeben.  
  
> [!NOTE]
>  Sie sollten nicht in das Dokument Destruktor Dokumentdaten freigeben. Bei einer SDI-Anwendung könnte das Dokumentobjekt wiederverwendet werden.  
  
 Sie können eine Ansicht Destruktor, um Arbeitsspeicher freizugeben, die Sie auf dem Heap reserviert überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

