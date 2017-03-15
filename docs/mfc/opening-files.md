---
title: "&#214;ffnen von Dateien | Microsoft Docs"
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
  - "CFile-Klasse, Variable"
  - "Beispiele [MFC], Öffnen von Dateien"
  - "Ausnahmebehandlung [C++], Öffnen von Dateien"
  - "Ausnahmebehandlung [C++], beim Öffnen von Dateien"
  - "Dateiobjekte [C++]"
  - "Dateien [C++], Öffnen"
  - "MFC [C++], Dateivorgänge"
  - "Offene Aufrufe"
  - "Offene Memberfunktionen"
  - "Open-Methode, CFile-Klasse"
  - "Öffnen von Dateien"
  - "Öffnen von Dateien, Ausnahmebehandlung"
  - "Öffnen von Dateien, in MFC"
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#214;ffnen von Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In MFC ist die gängigste Methode, eine Datei zu öffnen ein zweistufiger Prozess.  
  
#### So laden Sie eine Datei öffnen  
  
1.  Erstellen Sie das Dateiobjekt, ohne einem Pfad oder Berechtigungsflags anzugeben.  
  
     Sie erstellen in der Regel ein Dateiobjekt, indem Sie eine Variable [Die C\-Datei](../mfc/reference/cfile-class.md) auf dem Stapelrahmen deklarieren.  
  
2.  Rufen Sie die Memberfunktion [Öffnen](../Topic/CFile::Open.md) für das Dateiobjekt auf und einem Pfad und Berechtigungsflags angeben.  
  
     Der Rückgabewert von `Open` ist ungleich 0 \(null\), wenn die Datei erfolgreich oder 0 geöffnet war, wenn die angegebene Datei nicht geöffnet werden kann.  Die `Open`\-Memberfunktion wird einen Prototyp entwickelt, wie folgt:  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Die offenen Flags geben an, die Berechtigungen, z schreibgeschütztes, Sie für die Datei soll.  Mögliche Flagwerte werden als Konstanten der Enumeration innerhalb der `CFile`\-Klasse definiert, sodass sie mit "`CFile::`" wie in `CFile::modeRead` qualifiziert.  Verwenden Sie das `CFile::modeCreate`\-Flag, wenn Sie die Datei erstellen möchten.  
  
 Das folgende Beispiel zeigt, wie eine neue Datei mit Lese\-\/Schreibberechtigung erstellt \(der vorherige eine Datei mit demselben Pfad ersetzen\):  
  
 [!CODE [NVC_MFCFiles#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCFiles#1)]  
  
> [!NOTE]
>  Dieses Beispiel erstellt und öffnet eine Datei.  Wenn es dabei Probleme gibt, kann der Aufruf `Open` in einem `CFileException`\-Objekt seiner letzten Parameter zurückgeben, wie hier gezeigt.  Das `TRACE`\-Makro gibt den Dateinamen und einen Code, die den Grund für Fehler angeben.  Sie können die Funktion `AfxThrowFileException` aufrufen, wenn Sie einen Fehlerbericht benötigen.  
  
## Siehe auch  
 [CFile Class](../mfc/reference/cfile-class.md)   
 [CFile::Open](../Topic/CFile::Open.md)   
 [Dateien](../mfc/files-in-mfc.md)