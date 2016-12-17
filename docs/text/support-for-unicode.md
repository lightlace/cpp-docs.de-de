---
title: "Unterst&#252;tzung f&#252;r Unicode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichensätze [C++], Unicode"
  - "Globalisierung [C++], Zeichensätze"
  - "Lokalisierung [C++], Zeichensätze"
  - "Portable Datentypen [MFC]"
  - "Unicode [C++]"
  - "Unicode [C++], Installationshilfe"
  - "Breitzeichen [C++], Informationen über Breitzeichen"
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "ghogen"
manager: "ghogen"
---
# Unterst&#252;tzung f&#252;r Unicode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unicode ist eine Spezifikation für die Unterstützung aller Zeichensätze, einschließlich solcher, die nicht mit nur einem Byte dargestellt werden können.  Wenn Sie für einen internationalen Markt programmieren, wird empfohlen, Unicode oder [Multibytezeichensätze](../text/support-for-multibyte-character-sets-mbcss.md) \(MBCSs\) zu verwenden oder Ihr Programm so zu programmieren, dass Sie es für beides erstellen können, indem Sie einen Switch ändern.  
  
 Ein Breitzeichen ist ein mehrsprachiger 2\-Byte\-Zeichencode.  Die meisten in der modernen Computerwelt verwendeten Zeichen, einschließlich technischer Symbole und spezieller Veröffentlichungszeichen, können nach der Unicode\-Spezifikation als Breitzeichen dargestellt werden.  Zeichen, die nicht mit nur einem Breitzeichen dargestellt werden können, können in einem Unicode\-Paar mit der Unicode\-Ersatzzeichenfunktion dargestellt werden.  Da jedes Breitzeichen in einer festen Größe von 16 Bits dargestellt wird, vereinfacht die Verwendung von Breitzeichen die Programmierung mit internationalen Zeichensätzen.  
  
 Eine Breitzeichenzeichenfolge wird als **wchar\_t\[\]**\-Array dargestellt, auf das mit einem `wchar_t*`\-Zeiger gezeigt wird.  Jedes ASCII\-Zeichen kann als Breitzeichen dargestellt werden, indem der Buchstabe L dem Zeichen vorangestellt wird.  L'\\0' ist beispielsweise das abschließende \(16\-Bit\) **NULL**\-Breitzeichen.  Auf ähnliche Weise kann jedes ASCII\-Zeichenfolgenliteral als Breitzeichen\-Zeichenfolgenliteral dargestellt werden, indem der Buchstabe L dem ASCII\-Literal vorangestellt wird \(L"Hello"\).  
  
 Im Allgemeinen benötigen Breitzeichen mehr Platz im Arbeitsspeicher als Multibytezeichen, werden aber schneller verarbeitet.  Darüber hinaus kann jeweils nur ein Gebietsschema in der Multibytecodierung dargestellt werden, während alle Zeichensätze der Welt gleichzeitig von der Unicode\-Darstellung dargestellt werden können.  
  
 Das MFC\-Framework ist komplett Unicode\-fähig, und MFC erreicht die Unicode\-Fähigkeit durch die Verwendung von portablen Makros, die in der folgenden Tabelle gezeigt sind.  
  
### Portable Datentypen in MFC  
  
|Nicht portable Datendatentypen|Ersetzt durch dieses Makro|  
|------------------------------------|--------------------------------|  
|`char`|\_**TCHAR**|  
|**char\***, **LPSTR \(Win32\-Datentyp\)**|`LPTSTR`|  
|**const char\*, LPCSTR \(Win32\-Datentyp\)**|`LPCTSTR`|  
  
 Die Klasse `CString` verwendet **\_TCHAR** als Basis und stellt Konstruktoren und Operatoren für einfache Konvertierungen bereit.  Die meisten Zeichenfolgenvorgänge für Unicode können durch dieselbe Logik geschrieben werden, die für die Verarbeitung des Windows\-ANSI\-Zeichensatzes verwendet wird, mit der Ausnahme, dass die grundlegende Einheit für Vorgänge ein 16\-Bit\-Zeichen anstelle eines 8\-Bit\-Zeichens ist.  Im Gegensatz zur Arbeit mit Multibytezeichensätzen müssen \(und sollten\) Sie ein Unicode\-Zeichen nicht behandeln, als bestünde es aus zwei unterschiedlichen Bytes.  
  
## Was möchten Sie tun?  
  
-   [Installieren der Unicode\-Unterstützung über MFC](../mfc/unicode-in-mfc.md)  
  
-   [Aktivieren von Unicode im Programm](../text/international-enabling.md)  
  
-   [Sowohl Unicode als auch MBCS im Programm aktivieren](../text/internationalization-strategies.md)  
  
-   [Verwenden von Unicode zum Erstellen eines internationalen Programms](../text/unicode-programming-summary.md)  
  
-   [Vorteile von Unicode, einschließlich der Frage, wie Unicode ein Programm in Windows 2000 effizienter macht](../text/benefits-of-character-set-portability.md)  
  
-   [Verwenden von wmain zum Übergeben von Breitzeichenargumenten an ein Programm](../text/support-for-using-wmain.md)  
  
-   [Anzeigen einer Zusammenfassung zur Unicode\-Programmierung](../text/unicode-programming-summary.md)  
  
-   [Etwas über die Zuordnungen generischer Texte bei Byte\-breiter Portabilität erfahren](../text/generic-text-mappings-in-tchar-h.md)  
  
## Siehe auch  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)   
 [Unterstützung für die Verwendung von wmain](../text/support-for-using-wmain.md)