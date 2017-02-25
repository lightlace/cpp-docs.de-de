---
title: "Unterst&#252;tzung f&#252;r Unicode- und Multibyte-Zeichens&#228;tze (MBCS) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC [C++], Zeichensatzunterstützung"
  - "MBCS [C++], Zeichenfolgen und MFC-Unterstützung"
  - "Zeichenfolgen [C++], MBCS-Unterstützung in MFC"
  - "Zeichensätze [C++], Multibyte"
  - "Unicode [C++], MFC-Zeichenfolgen"
  - "Unicode [C++], Zeichenfolgenobjekte"
  - "Zeichenfolgen [C++], Unicode"
  - "Zeichenfolgen [C++], Zeichensatzunterstützung"
ms.assetid: 44b3193b-c92d-40c5-9fa8-5774da303cce
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Unterst&#252;tzung f&#252;r Unicode- und Multibyte-Zeichens&#228;tze (MBCS)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Einige Sprachen wie Japanisch und Chinesisch haben große Zeichensätze.  Um Programmierung für diese Märkte zu unterstützen, ist die Microsoft Foundation Class\-Bibliothek \(MFC\-Bibliothek\) so aktiviert, zwei unterschiedliche Ansätze zum Behandeln von umfangreichen Zeichensätzen verwendet werden können:  
  
-   [Unicode](#_core_mfc_support_for_unicode_strings)  
  
-   [Multibytezeichen \(MBCS\)](#_core_mfc_support_for_mbcs_strings)  
  
 Sie sollten für alle Neuentwicklungen Unicode verwenden.  
  
##  <a name="_core_mfc_support_for_unicode_strings"></a> MFC\-Unterstützung für Unicode\-Zeichenfolgen  
 Die gesamte Klassenbibliothek wird bedingt für Unicode\-Zeichen und \-Zeichenfolgen aktiviert.  Insbesondere ist Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode\-aktiviert.  
  
|||||  
|-|-|-|-|  
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|  
|MFC*xx*U.LIB|MFC*xx*U.PDB|MFC*xx*U.DLL|MFC*xx*UD.LIB|  
|MFC*xx*UD.PDB|MFC*xx*UD.DLL|MFCS*xx*U.LIB|MFCS*xx*U.PDB|  
|MFCS*xx*UD.LIB|MFCS*xx*UD.PDB|MFCM*xx*U.LIB|MFCM*xx*U.PDB|  
|MFCM*xx*U.DLL|MFCM*xx*UD.LIB|MFCM*xx*UD.PDB|MFCM*xx*UD.DLL|  
  
 \(*xx* stellt die Versionsnummer der Datei dar; "80" bedeutet z. B. Version 8.0.\)  
  
 `CString` basiert auf dem Datentyp `TCHAR`.  Wenn das Symbol `_UNICODE` für einen Build des Programms definiert ist, wird `TCHAR` als `wchar_t`\-Typ, ein 16\-Bit\-Zeichencodierungstyp, definiert.  Andernfalls wird `TCHAR` als `char`, die normale 8\-Bit\-Zeichencodierung, definiert.  Daher setzt sich ein `CString` unter Unicode aus 16\-Bit\-Zeichen zusammen.  Ohne Unicode wird es aus Zeichen vom Typ `char` zusammengesetzt.  
  
 Um Unicode\-Programmierung der Anwendung durchzuführen, benötigen Sie auch Folgendes:  
  
-   Verwenden Sie das `_T`\-Makro, um Zeichenfolgen bedingt so zu kodieren, dass sie in Unicode übertragbar sind.  
  
-   Wenn Sie Zeichenfolgen übergeben, achten Sie darauf, ob für Funktionsargumente eine bestimmte Länge in Zeichen oder in Bytes erforderlich.  Der Unterschied ist wichtig, wenn Sie Unicode\-Zeichenfolgen verwenden.  
  
-   Verwenden Sie portable Versionen der C\-Funktionen zur Behandlung von Zeichenfolgen zur Laufzeit.  
  
-   Verwenden Sie die folgenden Datentypen für Zeichen und Zeichenzeiger:  
  
    -   `TCHAR`. Hier verwenden Sie `char`.  
  
    -   `LPTSTR`. Hier verwenden Sie `char*`.  
  
    -   `LPCTSTR`. Hier verwenden Sie `const char*`.  `CString` stellt den Operator `LPCTSTR` zum Konvertieren zwischen `CString` und `LPCTSTR` bereit.  
  
 `CString` stellt außerdem Unicode\-kompatible Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren bereit.  
  
 Weitere Informationen zur Unicode\-Programmierung finden Sie unter den [Unicode\-Themen](../mfc/unicode-in-mfc.md).  Die [Laufzeitbibliotheksreferenz](../c-runtime-library/c-run-time-library-reference.md) definiert portable Versionen aller seiner Funktionen zur Behandlung von Zeichenfolgen.  Siehe die Kategorie [Internationalisierung](../c-runtime-library/internationalization.md).  
  
##  <a name="_core_mfc_support_for_mbcs_strings"></a> MFC\-Unterstützung für MBCS\-Zeichenfolgen  
  
> [!WARNING]
>  MBCS\-Zeichenfolgen sind veraltet und sollten in neuen Projekten nicht verwendet werden.  Die folgenden Informationen gelten für Szenarien, in denen Sie vorhandenen Code beibehalten müssen, der MBCS verwendet und nicht auf Unicode aktualisiert werden kann.  
  
 Die Klassenbibliothek wird auch für Multibyte\-Zeichensätze, jedoch nur für Doppelbyte\-Zeichensätze \(DBCS\) aktiviert.  
  
> [!IMPORTANT]
>  In [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] und höher, sind die MBCS\-Versionen der MFC\-DLLs nicht als freies Add\-In für Visual Studio auf der MSDN\-Downloadsite verfügbar.  Weitere Informationen finden Sie unter [MBCS\-Add\-In für MFC\-DLLs](../mfc/mfc-mbcs-dll-add-on.md).  
  
 In einem Multibyte\-Zeichensatz kann ein Zeichen ein oder zwei Bytes breit sein.  Wenn es zwei Bytes breit ist, ist sein erstes Byte ein spezielles "führendes Byte", das je nach verwendeter Codepage aus einem bestimmten Bereich ausgewählt wird.  Zusammen angewendet, geben die führenden und die "nachfolgenden Bytes" eine eindeutige Zeichencodierung an.  
  
 Wenn das Symbol `_MBCS` für einen Build des Programms definiert ist, wird der Typ `TCHAR`, auf dem `CString` basiert, `char` zugeordnet.  Sie bestimmen, welche Bytes in einer `CString` führende Bytes und welche nachfolgende Bytes sind.  Die Zubehörfunktionen der C\-Laufzeitbibliothek unterstützen Sie dabei.  
  
 Unter DBCS kann eine angegebene Zeichenfolge alle Einzelbyte\-ANSI\-Zeichen, alle Doppelbytezeichen oder eine Kombination der beiden enthalten.  Diese Methoden erfordern besondere Sorgfalt beim Parsen von Zeichenfolgen.  Hierzu gehören `CString`\-Objekte.  
  
> [!NOTE]
>  Mit der Serialisierung von Unicode\-Zeichenfolgen in MFC können sowohl Unicode als auch MBCS\-Zeichenfolgen unabhängig von der Version der Anwendung, die Sie ausführen, gelesen werden.  Die Datendateien sind zwischen Unicode\- und MBCS\-Versionen des Programms übertragbar.  
  
 `CString`\-Memberfunktionen verwenden spezielle Versionen der C\-Laufzeitfunktionen mit "generischem Text", die aufgerufen werden, oder sie verwenden Unicode\-kompatible Funktionen.  Wenn daher eine `CString`\-Funktion normalerweise `strcmp` aufrufen würde, ruft sie stattdessen die entsprechende Funktion `_tcscmp` für generischen Text auf.  Je nachdem, wie die Symbole `_MBCS` und `_UNICODE` definiert werden, wird `_tcscmp` wie folgt zugeordnet:  
  
|||  
|-|-|  
|`_MBCS` ist defined|`_mbscmp`|  
|`_UNICODE` ist definiert|`wcscmp`|  
|Kein Symbol definiert|`strcmp`|  
  
> [!NOTE]
>  Die Symbole `_MBCS` und `_UNICODE` schließen sich gegenseitig aus.  
  
 Funktionszuordnungen für generischen Text für alle Behandlungsroutinen für Ablaufzeichenfolgen werden in [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md) erläutert.  Siehe insbesondere [Internationalisierung](../c-runtime-library/internationalization.md).  
  
 Entsprechend werden `CString`\-Methoden implementiert, indem "generische" Datentypzuordnungen verwendet werden.  Um sowohl Unicode als auch MBCS zu aktivieren, verwendet MFC `TCHAR` für `char`, `LPTSTR` für `char*` und `LPCTSTR` für `const char*`.  Diese stellen die richtigen Zuordnungen für Unicode oder MBCS sicher.  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)   
 [Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md)