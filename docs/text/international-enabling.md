---
title: "Aktivierung der Internationalen Programmierung"
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
  - "Globalisierung [C++], Zeichensätze"
  - "Lokalisierung [C++], Zeichensätze"
  - "MBCS [C++], Aktivieren"
  - "Zeichenfolgen [C++], Aktivierung der Internationalen Programmierung"
  - "Unicode [C++], Aktivieren"
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# Aktivierung der Internationalen Programmierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Großteil des herkömmlichen C\- und C\+\+\-Codes wird bei der Bearbeitung von Zeichen und Zeichenfolgen von Annahmen ausgegangen, die für internationale Anwendungen ungeeignet sind.  Obwohl Unicode bzw. MBCS sowohl von MFC als auch von der Laufzeitbibliothek unterstützt wird, müssen Sie einige Aufgaben selbst ausführen.  Als Anhaltspunkt wird in diesem Abschnitt die Bedeutung der "Aktivierung der Internationalen Programmierung" in Visual C\+\+ erläutert:  
  
-   Unicode und MBCS werden mithilfe portabler Datentypen in den Parameterlisten und Rückgabetypen von MFC\-Funktionen aktiviert.  Diese Typen werden auf die entsprechende Weise bedingt definiert, abhängig davon, ob im jeweiligen Build das Symbol **\_UNICODE** oder das Symbol **\_MBCS** \(gleichbedeutend mit DBCS\) definiert wird.  Je nachdem, welches dieser beiden Symbole vom jeweiligen Build definiert wird, werden unterschiedliche Varianten der MFC\-Bibliotheken automatisch mit einer Anwendung verknüpft.  
  
-   Der Code der Klassenbibliotheken verwendet portable Laufzeitfunktionen und andere Mittel, um das richtige Unicode\- bzw. MBCS\-Verhalten sicherzustellen.  
  
-   Einige Aufgaben bezüglich der Internationalisierung müssen Sie im Code noch selbst durchführen.  
  
    -   Verwenden Sie dieselben portablen Laufzeitfunktionen, die dafür sorgen, dass MFC in beiden Umgebungen portabel ist.  
  
    -   Sorgen Sie durch Verwendung des **\_T**\-Makros dafür, dass Zeichenfolgenliterale und Zeichen in beiden Umgebungen portabel sind.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   Treffen Sie bei der Analyse von Zeichenfolgen unter MBCS geeignete Vorkehrungen.  Diese Vorkehrungen sind bei Unicode nicht erforderlich.  Weitere Informationen finden Sie unter [Tipps für die MBCS\-Programmierung](../text/mbcs-programming-tips.md).  
  
    -   Gehen Sie äußerst sorgfältig vor, wenn Sie in einer Anwendung sowohl ANSI\-Zeichen \(8 Bit\) als auch Unicode\-Zeichen \(16 Bit\) verwenden.  Es ist möglich, in einem Programmteil ANSI\-Zeichen und in einem anderen Teil Unicode\-Zeichen zu verwenden, die kombinierte Verwendung in derselben Zeichenfolge ist jedoch nicht möglich.  
  
    -   Führen Sie keinesfalls eine Hardcodierung der Zeichenfolgen in einer Anwendung durch.  Erstellen Sie diese stattdessen als STRINGTABLE\-Ressourcen, indem Sie sie der RC\-Datei der Anwendung hinzufügen.  Anschließend kann eine Anwendung lokalisiert werden; hierfür ist weder die Änderung noch die Neukompilierung des Quellcodes erforderlich.  Weitere Informationen über STRINGTABLE\-Ressourcen finden Sie in den Themen zum [Zeichenfolgen\-Editor](../mfc/string-editor.md).  
  
> [!NOTE]
>  Europäische Zeichensätze und MBCS\-Zeichensätze enthalten einige Zeichen, z. B. Buchstaben mit Akzent, deren Zeichencodes größer als 0x80 sind.  Da in den meisten Codes Zeichen mit Vorzeichen verwendet werden, weisen diese Zeichen, die größer als 0x80 sind, bei der Konvertierung nach `int` ein Vorzeichen auf.  Dies stellt ein Problem bei der Indizierung von Arrays dar, da die mit diesem Vorzeichen versehenen Zeichen negative Werte darstellen und die Indizes daher außerhalb des Arrays liegen.  Sprachen, die MBCS verwenden \(z. B. Japanisch\), sind ebenfalls eindeutig.  Da ein Zeichen aus 1 oder 2 Bytes bestehen kann, sollten Sie immer beide Bytes gleichzeitig bearbeiten.  
  
## Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Strategien für die Internationalisierung](../text/internationalization-strategies.md)