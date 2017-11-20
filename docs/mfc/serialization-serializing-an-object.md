---
title: 'Serialisierung: Serialisieren eines Objekts | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1339f7ab6b226da9f233e523171e318209e99ee4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="serialization-serializing-an-object"></a>Serialisierung: Serialisieren eines Objekts
Der Artikel [Serialisierung: Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md) wird gezeigt, wie eine Klasse serialisierbar zu machen. Nachdem Sie eine serialisierbare Klasse haben, können Sie Objekte dieser Klasse andere und aus einer Datei über Serialisieren einer [CArchive](../mfc/reference/carchive-class.md) Objekt. In diesem Artikel wird Folgendes erläutert:  
  
-   [Ist ein CArchive-Objekt](../mfc/what-is-a-carchive-object.md).  
  
-   [Zwei Möglichkeiten zur Erstellung eines CArchive](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [Gewusst wie: verwenden die CArchive <\< und >> Operatoren](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [Speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Lassen Sie das Framework das Archiv für das serialisierbare Dokument zu erstellen, oder erstellen Sie explizit die `CArchive` selbst. Übertragen Daten zwischen einer Datei und dem serialisierbaren Objekt mit der <\< und >> Operatoren für `CArchive` oder in einigen Fällen durch Aufrufen der `Serialize` Funktion eine `CObject`-abgeleitete Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung](../mfc/serialization-in-mfc.md)

