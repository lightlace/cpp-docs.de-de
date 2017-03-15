---
title: "Serialisierung in MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umgehen von Serialisierung"
  - "Auflistungsklassen, Serialisierung"
  - "MFC, Serialisierung"
  - "Serialisierung [C++], Umgehen"
  - "Serialisierung [C++], MFC"
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Serialisierung in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt den Serialisierungsmechanismus, der in der Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\) bereitgestellt wird von Objekten ermöglichen, zwischen den Ausführungszyklen des Programms beibehalten werden sollen.  
  
 Serialisierung ist der Prozess des Schreibens oder der Lesen ein Objekt zu bzw. aus einem permanenten Speichermedium des Speichers wie einer Datenträgerdatei.  Serialisierung ist für Situationen geeignet, in denen dies erforderlich ist, um den Zustand von strukturierten Daten \(z C\+\+\-Klassen oder Strukturen vorgestellt\) während oder nach Programmausführung beizubehalten.  Verwenden der Serialisierungsobjekte, die von MFC bereitgestellte sind, lässt diesem, um in einer Standard\- und konsistente Weise fungieren und entlastet den Benutzer von der Anforderung, Dateioperationen manuell auszuführen.  
  
 MFC stellt integrierte Unterstützung für Serialisierung in der Klasse `CObject`.  Daher können alle Klassen, die von `CObject` abgeleitet werden, `CObject` Serialisierungsprotokoll nutzen.  
  
 Die Grundidee der Serialisierung ist, dass ein Objekt in der Lage sein sollte, den aktuellen Zustand zu schreiben, normalerweise angegeben durch den Wert ihrer Membervariablen, permanenten Speicher.  Später kann das Objekt neu erstellt werden, indem liest, oder, der sein Zustand aus dem Speicher deserialisiert.  Serialisierung behandelt alle Details der Objektzeigern und Zirkelverweise zu den Objekten, die verwendet werden, wenn Sie ein Objekt serialisieren.  A\-TASTEen\-Punkt ist, dass das Objekt selbst für das Lesen und Schreiben von eigenen Zustand zuständig ist.  Daher kann eine Klasse serialisierbar ist, muss er die grundlegenden Serialisierungsvorgänge implementieren.  Wie in der Serialisierungsgruppe von Artikeln dargestellt, ist es einfach, dieser Funktionalität einer Klasse.  
  
 MFC verwendet ein Objekt der `CArchive`\-Klasse als Vermittler zwischen dem Objekt, serialisiert werden und dem Speichermedium.  Dieses Objekt wird immer mit einem `CFile`\-Objekt zugeordnet, von dem die erforderlichen Informationen für Serialisierung, einschließlich des Dateinamens einholt und ob der angeforderten Operation ein Lese\- ist, oder schreiben Sie.  Das Objekt, das einen Serialisierungsvorgang ausgeführt wird, kann das `CArchive`\-Objekt ohne Berücksichtigung der Art des Speichermediums verwenden.  
  
 Ein `CArchive`\-Objekt verwendet überladene Operatoren Einfüge\- \(**\<\<**\) und von Extraktions\- \(**\>\>**\), zum Schreiben und Lesenvorgänge auszuführen.  Weitere Informationen finden Sie in Artikel [CObjects zu einem Archiv Speichern und Laden](../mfc/storing-and-loading-cobjects-via-an-archive.md) der Serialisierung: Serialisierung eines Objekts.  
  
> [!NOTE]
>  Verwechseln Sie die Klasse `CArchive` nicht mit allgemeinen iostream\-Bibliothek Klassen, die nur zum formatierten Text sind.  Die `CArchive`\-Klasse ist für Binärformat serialisierte Objekte.  
  
 Wenn Sie möchten, können Sie MFC\-Serialisierung umgehen, um einen eigenen Mechanismus for Persistent Datenspeicherung zu erstellen.  Sie müssen den Klassenmember überschreiben arbeiten diese eingeleitete Serialisierung auf Weisung des Benutzers.  Siehe die Diskussion in der [Technischer Hinweis 22](../mfc/tn022-standard-commands-implementation.md) der `ID_FILE_OPEN`, **ID\_FILE\_SAVE** und **ID\_FILE\_SAVE\_AS** Standardbefehle.  
  
 Die folgenden Elemente gehören die zwei Hauptaufgaben, die für die Serialisierung erforderlich sind:  
  
-   [Serialisierung: Direkter eine serialisierbare Klasse](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)  
  
 Der Artikel [Serialisierung: Serialisierung für Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md) beschrieben, wann Serialisierung eine entsprechende Eingabe\/Ausgabe\-Technik in Datenbankanwendungen sind ist.  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [CArchive Class](../mfc/reference/carchive-class.md)   
 [CObject Class](../mfc/reference/cobject-class.md)   
 [CDocument Class](../mfc/reference/cdocument-class.md)   
 [CFile Class](../mfc/reference/cfile-class.md)