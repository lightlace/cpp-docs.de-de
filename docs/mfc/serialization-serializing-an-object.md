---
title: 'Serialisierung: Serialisieren eines Objekts | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3439857f14f4c4fa78aa2df3e3da8e5c8941938d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379657"
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

