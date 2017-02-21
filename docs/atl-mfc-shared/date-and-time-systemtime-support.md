---
title: "Datum und Uhrzeit: SYSTEMTIME-Unterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Systemuhrzeit"
  - "FILETIME-Struktur mit CTime-Klasse"
  - "Uhrzeitformat [C++]"
  - "SYSTEMTIME-Struktur"
  - "MFC-Daten [C++]"
  - "Formatierung [C++], Zeit"
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Datum und Uhrzeit: SYSTEMTIME-Unterst&#252;tzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die [CTime](../atl-mfc-shared/reference/ctime-class.md) -Klasse verfügt über Konstruktoren, die System- und Dateizeiten von Win32 akzeptieren. Wenn Sie `CTime`-Objekte zu diesem Zweck verwenden, müssen Sie deren Initialisierung entsprechend anpassen, wie in diesem Artikel beschrieben.  
  
 Informationen zur SYSTEMTIME-Struktur finden Sie unter [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). Informationen zur FILETIME-Struktur finden Sie unter [FILETIME](../mfc/reference/filetime-structure.md).  
  
 MFC bietet weiterhin `CTime`-Konstruktoren, die Argumente im MS-DOS-Format akzeptieren. Ab MFC-Version 3.0 unterstützt die `CTime`-Klasse jedoch auch einen Konstruktor, der eine Win32-`SYSTEMTIME`-Struktur akzeptiert, und einen anderen, der eine Win32-`FILETIME`-Struktur akzeptiert.  
  
 Die neuen `CTime`-Konstruktoren sind:  
  
-   CTime (const SYSTEMTIME & `sysTime`);  
  
-   CTime (const FILETIME & `fileTime`);  
  
 Der `fileTime`-Parameter ist ein Verweis auf eine Win32-`FILETIME`-Struktur, die die Zeit als einen 64-Bit-Wert darstellt. Dabei handelt es sich um ein zweckmäßigeres Format für die interne Speicherung als eine `SYSTEMTIME`-Struktur und das von Win32 verwendete Format zur Darstellung der Dateierstellungszeit.  
  
 Wenn Ihr Code ein `CTime`-Objekt enthält, das mit der Systemzeit initialisiert wurde, sollten Sie unter Win32 den `SYSTEMTIME`-Konstruktor verwenden.  
  
 Verwenden Sie wahrscheinlich nicht `CTime` `FILETIME` -Initialisierung direkt. Bei Verwendung einer `CFile` Objekt um eine Datei zu manipulieren [CFile:: GetStatus](../mfc/reference/cfile-class.md#getstatus) Timestamp der Datei abgerufen, für die Sie über ein `CTime` Objekt initialisiert wird, mit einer `FILETIME` Struktur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Allgemeine Datums- und zeitprogrammierung in MFC](../atl-mfc-shared/date-and-time.md)  
  
-   [Benutzeroberflächenautomatisierungs-Unterstützung von Datums- und zeitprogrammierung](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Allgemeine Klassen für die Datums- und zeitprogrammierung](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)

