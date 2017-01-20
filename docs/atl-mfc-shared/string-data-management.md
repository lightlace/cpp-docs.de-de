---
title: "String Data Management"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, string objects"
ms.assetid: 0b53a542-eeb1-4108-9ada-6700645b6f8f
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# String Data Management
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ bietet mehrere Möglichkeiten, Zeichenfolgendaten zu verwalten:  
  
-   [Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md) für das Arbeiten mit auf NULL endende Zeichenfolgen in C\-Format  
  
-   Win32\-API\-Funktionen zum Verwalten von Zeichenfolgen  
  
-   \- Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md) MFC, die die flexiblen, in der Größe veränderbaren Zeichenfolgenobjekte stellt  
  
-   \- Klasse [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md), die ein MFC\-unabhängiges Zeichenfolgenobjekt mit den gleichen Funktionen wie `CString` stellt  
  
 Fast alle Programmarbeit mit Zeichenfolgendaten.  `CString`\-Klasse MFC ist häufig die beste Lösung für flexible Zeichenfolgenbehandlung.  Ab Version 7.0, kann `CString` in MFC oder in den MFC\-unabhängigen Programmen verwendet werden.  unterstützen die Laufzeitbibliothek und `CString` die Zeichenfolgen, die enthalten \(breite\) Zeichen, wie in Unicode oder im MBCS\-Programmierung.  
  
 In diesem Artikel werden die allgemeinen Dienste, die die Klassenbibliothek verwandtes zur Zeichenfolgenbearbeitung bereitstellt.  Themen beschrieben in diesem Artikeleinschliessung:  
  
-   [Unicode und MBCS stellt Portabilität](#_core_unicode_and_mbcs_provide_portability)  
  
-   [CStrings und const verkohlen Zeiger](#_core_cstrings_and_const_char_pointers)  
  
-   [CString\-Verweiszählung](#_core_cstring_reference_counting)  
  
 Die [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)\-Klasse bietet Unterstützung für das Bearbeiten von Zeichenfolgen.  Es soll, um die Funktionen zu ersetzen und zu erweitern, die normalerweise vom C\-Laufzeitbibliotheks\-Zeichenfolgenpaket bereitgestellt wird.  Die `CString`\-Klassenzubehörmemberfunktionen und Operatoren für vereinfachte Zeichenfolgenbehandlung, ähnlich denen gefunden in Basic.  Die Klasse stellt auch Konstruktoren und Operatoren für das Erstellen, das Zuweisen und das Vergleichen von **CStrings** und von Standard\-C\+\+\-String\-Datentypen bereit.  Da `CString` nicht von `CObject` abgeleitet ist, können Sie `CString`\-Objekte unabhängig die meisten der Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\) verwenden.  
  
 `CString`\-Objekte folgen "Wertsemantik bezeichnet." Ein Objekt `CString` stellt einen eindeutigen Wert dar.  Wägen Sie `CString` als tatsächliche Zeichenfolge, nicht als Zeiger auf eine Zeichenfolge.  
  
 Ein Objekt `CString` stellt eine Sequenz einer variablen Anzahl von Zeichen dar.  `CString`\-Objekte können für Arrays Zeichen betrachtet werden.  
  
##  <a name="_core_unicode_and_mbcs_provide_portability"></a> Unicode und MBCS stellt Portabilität  
 Mit MFC, Version 3.0 wird MFC, einschließlich `CString`, für Unicode und Mehrbyte\-Zeichensätze \(MBCS\) aktiviert.  Diese Unterstützung vereinfacht, sodass Sie portable Anwendungen schreiben, die Sie für Unicode oder ANSI\-Zeichen erstellen können entweder.  Um diese Portabilität aktivieren, wird jedes Zeichen in einem `CString`\-Objekt vom Typ **TCHAR**, der als `wchar_t` definiert wird, wenn Sie das Symbol **\_UNICODE** definieren, wenn Sie die Anwendung erstellen, oder als `char` wenn nicht.  Ein `wchar_t` Zeichen ist 16 Bits breit.  MBCS ist aktiviert, wenn Sie mit dem Symbol **\_MBCS** definierten erstellen.  MFC selbst wird entweder mit dem **\_MBCS** Symbol \(für die NAFX\-Bibliotheken\) oder dem **\_UNICODE** Symbol \(für die UAFX\-Bibliotheken definiert\) erstellt.  
  
> [!NOTE]
>  Die Beispiele in diesem `CString` und die begleitenden Artikel auf Zeichenfolgen zeigen die Literalzeichenfolgen an, die ordnungsgemäß für Unicode\-Portabilität, mithilfe des **\_T**\-Makros formatiert werden, das die Zeichenfolgenliteral in Formular übersetzt:  
  
 `L"literal string"`  
  
> [!NOTE]
>  welches der Compiler als Unicode\-Zeichenfolge behandelt.  Folgender Code z. B.:  
  
 [!CODE [NVC_ATLMFC_Utilities#187](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#187)]  
  
> [!NOTE]
>  wird als Unicode\-Zeichenfolge übersetzt, wenn **\_UNICODE** oder als ANSI\-Zeichenfolge wenn nicht definiert ist.  Weitere Informationen finden Sie im Artikel [Unterstützung für Unicode\- und Multibyte\-Zeichensätze \(MBCS\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
 Ein Objekt `CString` kann bis zu **INT\_MAX** \(2.147.483.647\) Zeichen speichern.  Der **TCHAR** Datentyp wird verwendet, um abzurufen, oder, einzelne Zeichen innerhalb `CString` festzulegen Objekts.  Anders als Zeichenarrays hat die `CString`\-Klasse eine integrierte Speicherbelegungsfunktion.  Dadurch können `CString`\-Objekte, um automatisch nach Bedarf vergrößert \(das heißt, müssen Sie nicht um das Wachsen eines Objekts `CString` zu den entsprechenden längeren Zeichenfolgen zu kümmern\).  
  
##  <a name="_core_cstrings_and_const_char_pointers"></a> CStrings und const verkohlen Zeiger  
 Ein Objekt `CString` kann wie eine literale Zeichenfolge im C\-Format \( `PCXSTR`, die mit identisch **const char\*** wenn nicht mit Unicode ist\) auch verhalten.  Der [CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md) Konvertierungsoperator können für Zeichenzeiger in Funktionsaufrufen frei ersetzt werden `CString`\-Objekte.  Der Konstruktor **CString\( LPCWSTR**`pszSrc`**\)** ermöglicht die für `CString`\-Objekte ersetzt werden Zeichenzeiger.  
  
 Es wird nicht versucht, `CString`\-Objekte zu falten gemacht.  Wenn Sie zwei `CString`\-Objekte ausführen, die `Chicago` beispielsweise enthalten werden die Zeichen in `Chicago` an zwei Stellen gespeichert.  \(Dies ist nicht true von zukünftigen Versionen von MFC, sollten Sie nicht davon abhängen.\)  
  
> [!NOTE]
>  Verwenden Sie die [CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) und [CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)\-Memberfunktionen, wenn Sie auf `CString` als nicht konstanter Zeiger auf ein Zeichen direkt zugreifen müssen.  
  
> [!NOTE]
>  Verwenden Sie die [CStringT::AllocSysString](../Topic/CStringT::AllocSysString.md) und [CStringT::SetSysString](../Topic/CStringT::SetSysString.md)\-Memberfunktionen, um `BSTR`\-Objekte reserviert und festzulegen, die in der Automatisierung verwendet werden \(früher bekannt als OLE\-Automatisierung\).  
  
> [!NOTE]
>  Ordnen Sie nach Möglichkeit `CString`\-Objekte auf den Frame statt auf dem Heap zu.  Dies spart Arbeitsspeicher und vereinfacht das Parameterübergabe.  
  
 Die `CString`\-Klasse wird nicht als Microsoft Foundation Class\-Bibliothek\-Auflistungsklasse implementiert, obwohl `CString`\-Objekte als Elemente in Auflistungen zweifellos gespeichert werden können.  
  
##  <a name="_core_cstring_reference_counting"></a> CString\-Verweiszählung  
 Ab MFC 4.0, wenn [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)\-Objekte kopiert werden, erhöht MFC einen Verweiszähler, anstatt die Daten zu kopieren.  Dies macht das Übergeben von Parametern durch einen Wert und die Rückgabe von `CString`\-Objekten durch den effizienteren Wert.  Diese Vorgänge werden den Kopierkonstruktor, manchmal mehrmals aufgerufen werden.  Erstellen eines Verweiszähler inkrementierend reduziert, dass Mehraufwand für diese allgemeinen Vorgänge und arbeitet mit `CString` eine attraktivere Option.  
  
 Während jede Kopie zerstört wird, wird der Verweiszähler im ursprünglichen Objekt verringert.  Das ursprüngliche `CString`\-Objekt wird nicht zerstört, bis dessen Verweiszähler auf Null reduziert ist.  
  
 Sie können die `CString`\-Memberfunktionen [CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md) und [CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md) verwenden, um Komponenten zu deaktivieren oder zu aktivieren.  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)