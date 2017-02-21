---
title: "Unterst&#252;tzung von Mehrbyte-Zeichens&#228;tzen (MBCS) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichensätze [C++], Mehrbyte"
  - "MBCS [C++]"
  - "MBCS [C++], Informationen über MBCS"
  - "Mehrbytezeichen [C++]"
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Unterst&#252;tzung von Mehrbyte-Zeichens&#228;tzen (MBCS)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mehrbyte\-Zeichensätze \(MBCS\) sind ein älterer Ansatz, mit dem die erforderliche Unterstützung von Zeichensätzen sichergestellt wird, die nicht mit einem Byte pro Zeichen dargestellt werden können, z. B. Japanisch und Chinesisch.  Wenn Sie Neuentwicklungen ausführen, sollten Sie Unicode für alle Textzeichenfolgen außer Systemzeichenfolgen verwenden, die nicht für die Endbenutzer sichtbar sind.  MBCS ist eine ältere Technologie und wird nicht für Neuentwicklungen empfohlen.  
  
 Bei den gängigsten MBCS\-Implementierungen handelt es sich um Doppelbyte\-Zeichensätze \(DBCS\).  Visual C\+\+ im Allgemeinen und MFC im Besonderen sind vollständig DBCS\-aktiviert.  
  
> [!WARNING]
>  In Visual Studio 2013 und höher werden die MFC\-Bibliotheken für Multibyte\-Zeichencodierung \(MBCS\) als Add\-Ons zu Visual Studio bereitgestellt und sind kostenlos für Visual Studio\-Kunden \(nur Pro\- und Enterprise\-Editionen\) auf der MSDN\-Downloadsite verfügbar.  
>   
>  Für die Bibliotheken sind ungefähr 440 MB auf dem Laufwerk erforderlich, und die Installation umfasst alle lokalisierten Versionen der Bibliotheken.  Sie können sie auf jedem Computer installieren, auf dem die Edition Visual Studio Community, Professional oder Enterprise installiert ist und auf dem die MFC\-Funktion für den Posteingang aktiviert ist.  
>   
>  Wenn Sie Visual Studio deinstallieren oder reparieren, werden die MBCS\-Bibliotheken ebenfalls deinstalliert oder korrigiert.  Wenn Sie jedoch die MFC\-Funktion entfernen, bleiben die MBCS\-Bibliotheken im System.  Wenn Sie die MBCS\-Bibliotheken reparieren, wird Visual Studio in keiner Weise geändert.  
>   
>  Die verteilbaren Pakete für Visual Studio 2013 und höher enthalten noch die DLLs für MBCS MFC.  Es sind keine zusätzlichen Schritte erforderlich, um die DLLs an die Kunden zu verteilen.  
  
 Beispiele finden Sie in den MFC\-Quellcodedateien.  
  
 Für Plattformen, die in Ländern mit umfangreichen Zeichensätzen verwendet werden, stellt MBCS die beste Alternative zu Unicode dar.  MFC unterstützt MBCS durch Verwendung internationalisierbarer Datentypen und C\-Laufzeitfunktionen.  Es empfiehlt sich, im Code ebenso vorzugehen.  
  
 Unter MBCS werden Zeichen in ein oder zwei Bytes codiert.  In zwei Bytes breiten Zeichen zeigt das erste oder führende Byte an, dass es selbst und das nächste Byte als ein einziges Zeichen zu interpretieren sind.  Das erste Byte stammt aus einem Bereich mit Codes, die zur Verwendung als führende Bytes reserviert sind.  Welche Bytebereiche als führende Bytes verwendet werden können, hängt von der jeweils verwendeten Codepage ab.  Von der japanischen Codepage 932 wird z. B. der Bereich von 0 x 81 bis 0 x 9 F für führende Bytes verwendet, während von der koreanischen Codepage 949 hierfür ein anderer Bereich verwendet wird.  
  
 Beachten Sie bei der MBCS\-Programmierung alle der nachfolgenden Punkte.  
  
 MBCS\-Zeichen in der Umgebung  
 MBCS\-Zeichen können in Dateinamen, Verzeichnisnamen und vergleichbaren Zeichenfolgen vorkommen.  
  
 Bearbeitungsvorgänge  
 Bearbeitungsvorgänge in MBCS\-Anwendungen sollten auf Zeichen und nicht auf Bytes basieren.  Von der Einfügemarke sollte kein Zeichen geteilt werden, mit der NACH RECHTS\-TASTE sollte man um ein Zeichen nach rechts gelangen usw.  Mit dem Befehl **Löschen** sollte ein Zeichen gelöscht werden; mit dem Befehl **Rückgängig** sollte dieses Zeichen erneut eingefügt werden.  
  
 Zeichenfolgenbehandlung  
 In Anwendungen, die MBCS verwenden, wirft die Behandlung von Zeichenfolgen besondere Probleme auf.  Da dieselbe Zeichenfolge breite und normale Zeichen enthalten kann, sind unbedingt Überprüfungen auf führende Bytes vorzusehen.  
  
 Unterstützung der Laufzeitbibliothek  
 Die C\-Laufzeitbibliothek und MFC unterstützen die Einzelbyte\-, MBCS\- und Unicode\-Programmierung.  Einzelbyte\-Zeichenfolgen werden mit Laufzeitfunktionen der `str`\-Reihe verarbeitet, MBCS\-Zeichenfolgen werden mit den entsprechenden `_mbs`\-Funktionen verarbeitet und Unicode\-Zeichenfolgen werden mit den entsprechenden *wcs*\-Funktionen verarbeitet.  In Implementierungen von Memberfunktionen der MFC\-Klasse werden portable Laufzeitfunktionen verwendet, die unter den richtigen Voraussetzungen der normalen `str`\-Funktionsreihe, den MBCS\-Funktionen oder den Unicode\-Funktionen zugeordnet werden, wie unter "MBCS\/Unicode\-Portabilität" beschrieben.  
  
 MBCS\/Unicode\-Portabilität  
 Mit der Headerdatei Tchar.h können Sie Einzelbyte\-, MBCS\- und Unicode\-Anwendungen aus denselben Quellen erstellen.  Tchar.h definiert Makros mit dem Präfix *\_tcs*, die je nach Bedarf `str`\-Funktionen, `_mbs`\-Funktionen oder *wcs*\-Funktionen zugeordnet werden.  Definieren Sie zur Erstellung von MBCS das **\_MBCS**\-Symbol.  Definieren Sie zur Erstellung von Unicode das **\_UNICODE**\-Symbol.  Standardmäßig wird **\_MBCS** für MFC\-Anwendungen definiert.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
> [!NOTE]
>  Wenn Sie sowohl **\_UNICODE** als auch **\_MBCS** definieren, ist das Verhalten nicht definiert.  
  
 Von den Headerdateien Mbctype.h und Mbstring.h werden MBCS\-spezifische Funktionen und Makros definiert, die in bestimmten Fällen benötigt werden.  Mit `_ismbblead` können Sie z. B. ermitteln, ob ein bestimmtes Byte einer Zeichenfolge ein führendes Byte ist.  
  
 Um ein Programm international portieren zu können, codieren Sie es mit [Unicode](../text/support-for-unicode.md) oder Mehrbyte\-Zeichensätzen \(MBCS\).  
  
## Wie möchten Sie vorgehen?  
  
-   [MBCS im Programm aktivieren](../text/international-enabling.md)  
  
-   [Sowohl Unicode als auch MBCS im Programm aktivieren](../text/internationalization-strategies.md)  
  
-   [MBCS verwenden, um ein internationales Programm zu erstellen](../text/mbcs-programming-tips.md)  
  
-   [Eine Zusammenfassung zur MBCS\-Programmierung ansehen](../text/mbcs-programming-tips.md)  
  
-   [Etwas über die Zuordnungen generischer Texte bei Byte\-breiter Portabilität erfahren](../text/generic-text-mappings-in-tchar-h.md)  
  
## Siehe auch  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)   
 [MBCS\-Unterstützung in Visual C\+\+](../text/mbcs-support-in-visual-cpp.md)