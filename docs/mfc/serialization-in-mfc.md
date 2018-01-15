---
title: Serialisierung in MFC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c648e32865f73bda5f896f26c495184f964c41d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-in-mfc"></a>Serialisierung in MFC
In diesem Artikel erläutert der Serialisierungsmechanismus verwenden, die in der Microsoft Foundation Class-Bibliothek (MFC) damit Objekte zwischen beibehalten werden können bereitgestellt des Programms ausgeführt wird.  
  
 Serialisierung ist der Prozess der Schreib- und Lesezugriffe auf ein Objekt auf oder von einem permanenten Speichermedium, z. B. eine Datenträgerdatei. Serialisierung ist ideal für Situationen, in denen es gewünscht ist, den Status der strukturierte Daten (z. B. C++-Klassen oder Strukturen) während oder nach der Ausführung eines Programms beibehalten. Mit den Serialisierungsinformationen von MFC bereitgestellten ermöglicht dies auf eine Weise standard und konsistent sind des Benutzers muss manuell Dateivorgänge ausführen.  
  
 MFC bietet integrierten Unterstützung für die Serialisierung in der Klasse `CObject`. Folglich alle Klassen abgeleitet `CObject` nutzen `CObject`des Serialisierungsprotokoll.  
  
 Das grundlegende Konzept der Serialisierung ist, dass ein Objekt seinen aktuellen Status, in der Regel bestimmt durch den Wert der zugehörigen Membervariablen, in den persistenten Speicher geschrieben werden sollten. Später kann das Objekt neu erstellt werden, indem gelesen oder deserialisiert, den Zustand des Objekts aus dem Speicher. Serialisierung behandelt alle Details der Objektzeigern und Zirkuläre Verweise auf Objekte, die beim Serialisieren eines Objekts verwendet werden. Ein wichtiger Punkt ist, dass das Objekt selbst für das Lesen und Schreiben von eigenen Status zuständig ist. Daher muss er für eine Klasse, die serialisierbar sein, die einfache Serialisierungsvorgänge implementieren. Wie in der Serialisierung Gruppe von Artikeln gezeigt, ist es einfach, diese Funktion auf eine Klasse hinzuzufügen.  
  
 MFC verwendet, ein Objekt von der `CArchive` Klasse als Mittler zwischen dem Objekt serialisiert werden und das Speichermedium. Dieses Objekt immer zugeordnet ist ein `CFile` Objekt, von dem aus sie die erforderlichen Informationen für die Serialisierung, einschließlich des Dateinamens abruft und gibt an, ob der angeforderte Vorgang eine Lese- oder Schreibzugriff ist. Das Objekt, das einen Serialisierungsvorgang ausführt, können die `CArchive` Objekt ohne Berücksichtigung der Art der Speichermedium.  
  
 Ein `CArchive` Objekt verwendet, überladene einfügen (**<\<**) und Extraktion (**>>**) Operatoren Schreib- und Lesevorgänge ausführen. Weitere Informationen finden Sie unter [speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md) im Artikel Serialisierung: Serialisieren eines Objekts.  
  
> [!NOTE]
>  Verwechseln Sie nicht die `CArchive` Klasse mit allgemeinen Iostream-Klassen, die für sind formatierten Text nur. Die `CArchive` Klasse ist für Binärformat serialisierten Objekte.  
  
 Wenn Sie möchten, können Sie die MFC-Serialisierung, um einen eigenen Mechanismus für die persistente Speicherung erstellen umgehen. Sie müssen die Memberfunktionen der Klasse zu überschreiben, die Serialisierung an den Benutzer zu initiieren. Finden Sie unter den Ausführungen im [technischen Hinweis 22](../mfc/tn022-standard-commands-implementation.md) von der `ID_FILE_OPEN`, **ID_FILE_SAVE**, und **ID_FILE_SAVE_AS** Standardbefehle.  
  
 Die folgenden Artikel behandelt die zwei Hauptaufgaben, die für die Serialisierung erforderlich:  
  
-   [Serialisierung: Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)  
  
 Der Artikel [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md) wird beschrieben, bei der Serialisierung eine entsprechende Eingabe/Ausgabe-Technik datenbankanwendungen ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [CArchive-Klasse](../mfc/reference/carchive-class.md)   
 [CObject-Klasse](../mfc/reference/cobject-class.md)   
 [CDocument-Klasse](../mfc/reference/cdocument-class.md)   
 [CFile-Klasse](../mfc/reference/cfile-class.md)
