---
title: "Zusammenfassung der Unicode-Programmierung | Microsoft Docs"
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
  - "Unicode [C++], MFC und C-Laufzeitfunktionen"
  - "Unicode [C++], Programmieren mit"
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Zusammenfassung der Unicode-Programmierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie von MFC\- und C\-Laufzeitunterstützung für Unicode profitieren möchten, müssen Sie folgende Schritte ausführen:  
  
-   Definieren Sie **\_UNICODE**.  
  
     Definieren Sie das **\_UNICODE**\-Symbol, bevor Sie ein Programm erstellen.  
  
-   Geben Sie den Einstiegspunkt an.  
  
     Legen Sie im Dialogfeld [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md) des Projekts im Ordner Linker auf der Seite **Ausgabe** das Einstiegspunkt\-Symbol auf **wWinMainCRTStartup** fest.  
  
-   Verwenden Sie portable Laufzeitfunktionen und Typen.  
  
     Verwenden Sie für die Behandlung von Unicode\-Zeichenfolgen die richtigen C\-Laufzeitfunktionen.  Sie können hierzu die **wcs**\-Funktionsreihe verwenden, aber auch die portablen \(für die internationale Programmierung aktivierten\) **\_TCHAR**\-Makros.  All diesen Makros ist **\_tcs** vorangestellt, sie sind gleichwertiger Ersatz für die **str**\-Funktionsreihe.  Eine detaillierte Beschreibung dieser Funktionen finden Sie im Abschnitt [Internationalisierung](../c-runtime-library/internationalization.md) der *Laufzeitbibliotheksreferenz*.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
     Verwenden Sie **\_TCHAR** und die verknüpften portablen Datentypen, wie unter [Unterstützung für Unicode](../text/support-for-unicode.md) beschrieben.  
  
-   Bearbeiten Sie Zeichenfolgenliterale vorschriftsmäßig.  
  
     Vom Visual C\+\+\-Compiler wird ein Zeichenfolgenliteral der Form  
  
    ```  
    L"this is a literal string"  
    ```  
  
     als Unicode\-Zeichenfolge interpretiert.  Sie können dasselbe Präfix für Literalzeichen verwenden.  Codieren Sie Zeichenfolgenliterale mithilfe des **\_T**\-Makros generisch, sodass sie mit Unicode als Unicode\-Zeichenfolgen, ohne Unicode jedoch als ANSI\-Zeichenfolgen \(einschließlich MBCS\) kompiliert werden.  Verwenden Sie z. B. nicht:  
  
    ```  
    pWnd->SetWindowText( "Hello" );  
    ```  
  
     sondern:  
  
    ```  
    pWnd->SetWindowText( _T("Hello") );  
    ```  
  
     Wenn **\_UNICODE** definiert ist, übersetzt **\_T** das Zeichenfolgenliteral in eine Zeichenfolge mit dem Präfix L, andernfalls wird es ohne dieses Präfix übersetzt.  
  
    > [!TIP]
    >  Die Makros **\_T** und `_TEXT` sind identisch.  
  
-   Gehen Sie beim Übergeben von Zeichenfolgenlängen an Funktionen mit Bedacht vor.  
  
     Bei einigen Funktionen muss die Anzahl der Zeichen in einer Zeichenfolge angegeben werden, bei anderen Funktionen die Anzahl der Bytes.  Wenn **\_UNICODE** definiert ist, schlägt folgender Aufruf von `CArchive` fehl \(`str` ist eine Zeichenfolge vom Typ `CString`\):  
  
    ```  
    archive.Write( str, str.GetLength( ) );    // invalid  
    ```  
  
     In einer Unicode\-Anwendung gibt die Länge die Zeichenanzahl, aber nicht die richtige Byte\-Anzahl an, da jedes Zeichen zwei Bytes breit ist.  Sie müssen also den obigen Funktionsaufruf wie folgt ändern:  
  
    ```  
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid  
    ```  
  
     Dieser Aufruf gibt fehlerfrei an, wie viele Bytes geschrieben werden sollen.  
  
     Zeichenorientierte MFC\-Memberfunktionen arbeiten jedoch im Gegensatz zu Byte\-orientierten Memberfunktionen ohne diese zusätzliche Codierung:  
  
    ```  
    pDC->TextOut( str, str.GetLength( ) );  
    ```  
  
     Für `CDC::TextOut` ist eine Anzahl von Zeichen, nicht eine Anzahl von Bytes erforderlich.  
  
-   Verwenden Sie [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), um Unicode\-Dateien zu öffnen.  
  
 Zusammenfassend bieten MFC und die Laufzeitbibliothek folgende Unterstützung für die Unicode\-Programmierung unter Windows 2000:  
  
-   Mit Ausnahme der Memberfunktionen für Datenbankklassen sind alle MFC\-Funktionen, einschließlich `CString`.  `CString` stellt darüber hinaus Unicode\/ANSI\-Konvertierungsfunktionen bereit.  
  
-   Die Laufzeitbibliothek stellt Unicode\-Versionen aller Funktionen zur Behandlung von Zeichenfolgen zur Verfügung. \(Die Laufzeitbibliothek enthält mit den \_tcs\-Makros auch portable, für Unicode  bzw. MBCS geeignete Versionen.\)  
  
-   Tchar.h stellt portable Datentypen und das **\_T**\-Makro zum Übersetzen von Zeichenfolgenliteralen und Zeichen bereit.  Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Die Laufzeitbibliothek enthält eine Breitzeichen\-Version von **main**.  Verwenden Sie **wmain**, um eine Anwendung Unicode\-kompatibel zu machen.  
  
## Siehe auch  
 [Unterstützung für Unicode](../text/support-for-unicode.md)