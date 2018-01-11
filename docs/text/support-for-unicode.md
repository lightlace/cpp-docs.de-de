---
title: "Unterstützung für Unicode | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 150f161b71efc07bc7b5a08d79e17fac0dea7931
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-unicode"></a>Unterstützung für Unicode
Unicode ist eine Spezifikation für die Unterstützung aller Zeichensätze, einschließlich solcher, die nicht mit nur einem Byte dargestellt werden können. Wenn Sie für einen internationalen Markt programmieren, es wird empfohlen, Sie entweder Unicode verwenden oder [Mehrbyte-Zeichensätzen](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS), oder das Programm zu aktivieren, können Sie es entweder eines Schalters erstellen.  
  
 Ein Breitzeichen ist ein mehrsprachiger 2-Byte-Zeichencode. Die meisten in der modernen Computerwelt verwendeten Zeichen, einschließlich technischer Symbole und spezieller Veröffentlichungszeichen, können nach der Unicode-Spezifikation als Breitzeichen dargestellt werden. Zeichen, die nicht mit nur einem Breitzeichen dargestellt werden können, können in einem Unicode-Paar mit der Unicode-Ersatzzeichenfunktion dargestellt werden. Da jedes Breitzeichen in einer festen Größe von 16 Bits dargestellt wird, vereinfacht die Verwendung von Breitzeichen die Programmierung mit internationalen Zeichensätzen.  
  
 Eine Zeichenfolge mit Breitzeichen wird als eine **Wchar_t []** array erstellt und zeigt eine `wchar_t*` Zeiger. Jedes ASCII-Zeichen kann als Breitzeichen dargestellt werden, indem der Buchstabe L dem Zeichen vorangestellt wird. L '\0' ist beispielsweise das abschließende (16-Bit) **NULL** Zeichen. Auf ähnliche Weise kann jedes ASCII-Zeichenfolgenliteral als Breitzeichen-Zeichenfolgenliteral dargestellt werden, indem der Buchstabe L dem ASCII-Literal vorangestellt wird (L"Hello").  
  
 Im Allgemeinen benötigen Breitzeichen mehr Platz im Arbeitsspeicher als Multibytezeichen, werden aber schneller verarbeitet. Darüber hinaus kann jeweils nur ein Gebietsschema in der Multibytecodierung dargestellt werden, während alle Zeichensätze der Welt gleichzeitig von der Unicode-Darstellung dargestellt werden können.  
  
 Das MFC-Framework ist komplett Unicode-fähig, und MFC erreicht die Unicode-Fähigkeit durch die Verwendung von portablen Makros, die in der folgenden Tabelle gezeigt sind.  
  
### <a name="portable-data-types-in-mfc"></a>Portable Datentypen in MFC  
  
|Nicht portable Datendatentypen|Ersetzt durch dieses Makro|  
|-----------------------------|----------------------------|  
|`char`|_**TCHAR**|  
|**Char\***, **LPSTR (Win32-Datentyp)**|`LPTSTR`|  
|**const Char\*, LPCSTR (Win32-Datentyp)**|`LPCTSTR`|  
  
 Klasse `CString` verwendet **_TCHAR** als Basis und stellt Konstruktoren und Operatoren für einfache Konvertierungen bereit. Die meisten Zeichenfolgenvorgänge für Unicode können durch dieselbe Logik geschrieben werden, die für die Verarbeitung des Windows-ANSI-Zeichensatzes verwendet wird, mit der Ausnahme, dass die grundlegende Einheit für Vorgänge ein 16-Bit-Zeichen anstelle eines 8-Bit-Zeichens ist. Im Gegensatz zur Arbeit mit Multibytezeichensätzen müssen (und sollten) Sie ein Unicode-Zeichen nicht behandeln, als bestünde es aus zwei unterschiedlichen Bytes.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Installieren von Unicode-Unterstützung über MFC](../mfc/unicode-in-mfc.md)  
  
-   [Unicode im Programm aktivieren](../text/international-enabling.md)  
  
-   [Sowohl Unicode-als auch MBCS im Programm aktivieren](../text/internationalization-strategies.md)  
  
-   [Verwenden von Unicode zum Erstellen eines internationalen Programms](../text/unicode-programming-summary.md)  
  
-   [Lernen Sie die Vorteile von Unicode, wie mithilfe von Unicode das Programm eine effizientere unter Windows 2000](../text/benefits-of-character-set-portability.md)  
  
-   [Verwenden von Wmain Breitzeichen-Argumente an ein Programm übergeben von breitzeichenargumenten](../text/support-for-using-wmain.md)  
  
-   [Finden Sie eine Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)  
  
-   [Erfahren Sie mehr über Zuordnungen für generischen Text für Byte-breiter Portabilität](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)   
 [Unterstützung für die Verwendung von wmain](../text/support-for-using-wmain.md)