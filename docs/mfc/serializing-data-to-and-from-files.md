---
title: Serialisieren von Daten in und aus Dateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], serialization
- documents [MFC], saving
- saving documents
- deserialization [MFC]
- serialization [MFC], role of document
- serialization [MFC], role of data
- data [MFC]
- data [MFC], serializing
- document data [MFC]
ms.assetid: b42a0c68-4bc4-4012-9938-5433a26d2c24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d28b12e19b302f5576d2cd76c931e0036c208185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="serializing-data-to-and-from-files"></a>Serialisieren von Daten in und aus Dateien
Das Grundkonzept von Persistenz ist, dass ein Objekt seinen aktuellen Status, angegeben durch die Werte ihrer Membervariablen, in den persistenten Speicher geschrieben werden sollten. Später kann das Objekt neu erstellt werden, indem gelesen oder "deserialisiert", den Zustand des Objekts aus dem permanenten Speicher. Ein wichtiger Punkt ist, dass das Objekt selbst für das Lesen und Schreiben von eigenen Status zuständig ist. Daher muss er für eine Klasse beibehalten werden, die einfache Serialisierungsvorgänge implementieren.  
  
 Das Framework stellt eine Standardimplementierung zum Speichern von Dokumenten in Datenträgerdateien, die als Antwort auf das Speichern und speichern unter Befehle im Menü Datei und zum Laden von Dokumenten über Datenträgerdateien als Antwort auf den Befehl öffnen. Mit sehr geringem Aufwand können Sie ein Dokument Möglichkeit zum Schreiben und lesen die Daten in und aus einer Datei implementieren. Das wichtigste notwendig ist, überschreiben die [Serialize](../mfc/reference/cobject-class.md#serialize) Memberfunktion in Ihr Dokumentklasse.  
  
 Die MFC-Anwendung-Assistent fügt eine skeletal Überschreibung der **CDocument** Memberfunktion `Serialize` in der Dokumentklasse, die für Sie erstellt. Nachdem Sie Ihre Anwendung Membervariablen implementiert haben, füllen Sie Ihrem `Serialize` außer Kraft setzen, durch Code, der die Daten auf ein "Archivobjekt" verbunden, die in eine Datei sendet. Ein [CArchive](../mfc/reference/carchive-class.md) Objekt ähnelt der `cin` und `cout` e/a-Objekte aus der C++-Iostream-Bibliothek. Allerdings `CArchive` schreibt und Binärformat nicht formatierter Text liest.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Serialisierung](../mfc/serialization-in-mfc.md)  
  
-   [Das Dokument Rolle bei der Serialisierung](#_core_the_document.92.s_role_in_serialization)  
  
-   [Die Daten der Rolle bei der Serialisierung](#_core_the_data.92.s_role_in_serialization)  
  
-   [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)  
  
##  <a name="_core_the_document.92.s_role_in_serialization"></a>Das Dokument Rolle bei der Serialisierung  
 Das Framework reagiert automatisch auf das Menü Datei öffnen, speichern, und speichern Sie als Befehle ein, durch den Aufruf des Dokuments `Serialize` Memberfunktion, wenn er implementiert wurde. Ein `ID_FILE_OPEN` Befehl ruft z. B. eine Handlerfunktion in der Application-Objekt. Während dieses Vorgangs wird angezeigt, und der Benutzer reagiert auf das Dialogfeld Datei öffnen, und das Framework Ruft den Dateinamen ein, den der Benutzer auswählt. Erstellt das Framework eine `CArchive` Objektsatz für Laden von Daten in das Dokument und übergibt das Archiv `Serialize`. Das Framework wurde die Datei bereits geöffnet. Der Code in Ihrem Dokuments `Serialize` Memberfunktion liest die Daten im durch das Archiv, rekonstruieren Datenobjekte nach Bedarf. Weitere Informationen zur Serialisierung finden Sie im Artikel [Serialisierung](../mfc/serialization-in-mfc.md).  
  
##  <a name="_core_the_data.92.s_role_in_serialization"></a>Die Daten der Rolle bei der Serialisierung  
 Im Allgemeinen sollten Klassentyp Daten selbst serialisieren können. D. h. Wenn Sie ein Objekt in ein Archiv übergeben, sollte das Objekt selbst schreiben in das Archiv und wie selbst aus dem Archiv gelesen kennen. MFC bietet Unterstützung für die Serialisierbarkeit von Klassen auf diese Weise. Wenn Sie entwerfen Sie eine Klasse, um einen Datentyp definieren, und Sie beabsichtigen, die Daten dieses Typs zu serialisieren, Entwerfen Sie für die Serialisierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

