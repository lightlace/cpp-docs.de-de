---
title: Bereinigen von Dokumenten und Ansichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f9bb1cbcb58e2693b33693b390a09d3826c77cfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cleaning-up-documents-and-views"></a>Bereinigen von Dokumenten und Ansichten
Wenn ein Dokument geschlossen wird, ruft das Framework zuerst die [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) Memberfunktion. Wenn Sie im Verlauf des Vorgangs für das Dokument, Arbeitsspeicher, der auf dem Heap zugeordnet `DeleteContents` ist der beste Ort, um ihn freizugeben.  
  
> [!NOTE]
>  Sie sollten nicht in das Dokument Destruktor Dokumentdaten freigeben. Bei einer SDI-Anwendung könnte das Dokumentobjekt wiederverwendet werden.  
  
 Sie können eine Ansicht Destruktor, um Arbeitsspeicher freizugeben, die Sie auf dem Heap reserviert überschreiben.  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

