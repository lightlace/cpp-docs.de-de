---
title: "Umgehen des Serialisierungsmechanismus | Microsoft Docs"
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
  - "Archivobjekte [C++]"
  - "Archive [C++]"
  - "Archive [C++], Serialisierung"
  - "Umgehen von Serialisierung"
  - "Serialisierung [C++], Umgehen"
  - "Serialisierung [C++], Überschreiben"
  - "Serialisierung [C++], Rolle des Frameworks"
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Umgehen des Serialisierungsmechanismus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie Sie gesehen haben, führt das Framework eine Standardmethode, Daten nach und Dateien zu lesen und zu schreiben.  Das Serialisieren durch ein Archivobjekt entspricht den Anforderungen von einem großen viele Anwendungen.  Eine solche Anwendung liest eine Datei vollständig in den Arbeitsspeicher, kann der Benutzer die Datei aktualisieren und schreibt die aktualisierte Version wieder auf den Datenträger.  
  
 Jedoch lassen einige Anwendungen an Daten sehr unterschiedlich werden ausgeführt, und für diese Anwendungen ist die Serialisierung von einem Archiv nicht geeignet.  Beispielseinschließungs\-Datenbankprogramme, Programme, die nur Teile große Dateien, Programme, die nur für Text Dateien schreiben und Programme bearbeiten, um die Datendateien freigeben.  
  
 In diesen Fällen können Sie die [Serialisieren Sie](../Topic/CObject::Serialize.md)\-Funktion in einer anderen Weise überschreiben, um Dateiaktionen durch ein [Die C\-Datei](../mfc/reference/cfile-class.md)\-Objekt statt [CArchive](../mfc/reference/carchive-class.md) ein Objekt zu übergeben.  
  
 Sie können **Öffnen**, **Lesen**, **Schreiben**, **Schließen** verwenden, und `Seek`\-Memberfunktionen der Klasse `CFile`, um eine Datei zu öffnen, der Dateizeiger \(Suche\) auf einen bestimmten Punkt in der Datei zu verschieben, Read\- einen Datensatz \(eine angegebene Anzahl Bytes\) an diesem Punkt, lassen den Benutzer den Datensatz aktualisieren, befindet auf denselben Punkt erneut und erstellen den Datensatz wieder auf die Datei.  Das Framework wird die Datei für Sie, und Sie können die `GetFile`\-Memberfunktion der `CArchive`\-Klasse verwenden, um einen Zeiger auf das `CFile`\-Objekt.  Für noch hoch entwickeltes und flexible Verwendung können Sie die [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) und [OnSaveDocument](../Topic/CDocument::OnSaveDocument.md) der `CWinApp`\-Memberfunktionen Klasse überschreiben.  Weitere Informationen finden Sie Klasse [Die C\-Datei](../mfc/reference/cfile-class.md) in der *MFC\-Referenz*.  
  
 In diesem Szenario wird die `Serialize` keine Überschreibung, es sei denn, dass, beispielsweise möchten Sie es den Dateiheader lesen und schreiben können, um den aktuell bleibt, wenn das Dokument schließt.  
  
## Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)