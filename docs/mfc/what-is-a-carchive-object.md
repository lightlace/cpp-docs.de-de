---
title: Was ist, dass ein CArchive-Objekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55b97843a8aeb2599d2bdf34458b362fc5899368
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383828"
---
# <a name="what-is-a-carchive-object"></a>Was ist ein CArchive-Objekt?
Ein `CArchive` Objekt als typsicherer Pufferung stellt einen Mechanismus bereit Schreib- und Lesezugriffe auf serialisierbare Objekte zu oder von einem `CFile` Objekt. In der Regel die `CFile` -Objekt stellt eine Datenträgerdatei dar; es kann jedoch auch sein einer Arbeitsspeicherdatei (`CSharedFile` Objekt), die Zwischenablage möglicherweise repräsentiert.  
  
 Ein angegebener `CArchive` Objekt entweder speichert (schreibt, serialisiert) Daten oder lädt (liest, deserialisiert) Daten, aber nicht beides. Die Lebensdauer einer `CArchive` Objekt auf einem einzigen Durchlauf durch die Objekte in eine Datei schreiben oder Lesen von Objekten aus einer Datei beschränkt ist. Daher zwei nacheinander erstellt `CArchive` Objekten sind erforderlich, um Daten in eine Datei zu serialisieren und Deserialisieren Sie ihn aus der Datei zurück.  
  
 Wenn ein Archiv Objekte in einer Datei speichert, fügt das Archiv der `CRuntimeClass` -Namens an die Objekte. Dann, wenn ein weiteres Archiv Objekte aus einer Datei in den Arbeitsspeicher, lädt die `CObject`-abgeleitete Objekte sind dynamisch rekonstruiert basierend auf der `CRuntimeClass` der Objekte. Ein angegebenes Objekt kann nur einmal verwiesen werden, wie es durch das Speichern von Archiv in die Datei geschrieben wird. Das Archiv laden, wird das Objekt jedoch nur einmal rekonstruieren. Die Details, wie ein Archiv fügt `CRuntimeClass` beschrieben, Informationen zu und rekonstruiert Objekte, und berücksichtigt möglich, mehrere Verweise sind [technischen Hinweis 2](../mfc/tn002-persistent-object-data-format.md).  
  
 Wie Daten in ein Archiv serialisiert werden, sammelt das Archiv die Daten, bis der Puffer voll ist. Dann das Archiv den Puffer in schreibt die `CFile` Objekt verweist das `CArchive` Objekt. Auf ähnliche Weise wie beim Lesen von Daten aus einem Archiv liest es Daten aus der Datei in den Puffer, und klicken Sie dann aus dem Puffer in das deserialisierte Objekt. Diese Pufferung reduziert die Anzahl der Häufigkeit, mit die eine Festplatte physisch gelesen wird, die damit die Leistung Ihrer Anwendung zu verbessern.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

