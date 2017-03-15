---
title: "Basic CString Operations | Microsoft Docs"
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
  - "Zeichen, accessing in CStrings"
  - "CString objects"
  - "CString objects, Grundlegende Vorgänge"
  - "literal strings, CString operations"
  - "Zeichenfolgenvergleich, CString operations"
  - "Zeichenfolgenliterale, CString operations"
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Basic CString Operations
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden die folgenden grundlegenden [CString](../atl-mfc-shared/reference/cstringt-class.md) Vorgänge:  
  
-   [Erstellen von CString\-Objekten von Standard\-C\-Literalzeichenfolgen](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
-   [Zugreifen auf einzelne Zeichen in einem CString](#_core_accessing_individual_characters_in_a_cstring)  
  
-   [Verketten von zwei CString\-Objekten](#_core_concatenating_two_cstring_objects)  
  
-   [Vergleichen von CString\-Objekten](#_core_comparing_cstring_objects)  
  
-   [Konvertieren von CString\-Objekten](#_core_converting_cstring_objects)  
  
 `Class CString` basiert auf Klassenvorlage [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md).  `CString` ist `typedef` von `CStringT`.  Genauer gesagt, ist `CString``typedef` einer *expliziten Spezialisierung* von `CStringT`, die eine allgemeine Methode besteht darin, eine Klassenvorlage verwenden, um eine Klasse definieren.  Entsprechend definierte Klassen sind `CStringA` und `CStringW`.  Weitere Informationen über explizite Spezialisierung, finden Sie unter [Klassenvorlageninstanziierung](../Topic/Class%20Template%20Instantiation.md).  
  
 `CString`, `CStringA` und `CStringW` werden in atlstr.h definiert.  `CStringT` wird in cstringt.h definiert.  
  
 `CString`, `CStringA` und `CStringW` jedes rufen einen Satz von Methoden und der Operatoren ab, die von `CStringT` zur Verwendung mit den Zeichenfolgendaten definiert werden, die sie unterstützen.  Ein Teil des Methodenduplikat und übertreffen in einigen Fällen die Zeichenfolgendienste der C\-Laufzeitbibliotheken.  
  
 Hinweis: `CString` ist eine systemeigene Klasse.  Eine Zeichenfolgenklasse, die für die Verwendung in verwaltetem ein C\/C\+\+\-Projekt \+\+\/CLI ist, verwenden Sie `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> Erstellen von CString\-Objekten von Standard\-C\-Literalzeichenfolgen  
 Sie können im C\-Format zuweisen `CString` Literalzeichenfolgen, wie Sie ein `CString`\-Objekt für andere zuweisen können.  
  
-   Weisen Sie den Wert von Wechselstrom\-Literalzeichenfolge zu einem `CString`\-Objekt zu.  
  
     [!CODE [NVC_ATLMFC_Utilities#183](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#183)]  
  
-   Weisen Sie den Wert von einem `CString` zu einem anderen `CString`\-Objekt zu.  
  
     [!CODE [NVC_ATLMFC_Utilities#184](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#184)]  
  
     Der Inhalt eines Objekts `CString` kopiert wird, wenn ein `CString`\-Objekt für andere zugewiesen wird.  Daher geben die beiden Zeichenfolgen keinen Verweis auf den tatsächlichen Zeichen frei, die die Zeichenfolge besteht.  Weitere Informationen dazu, wie `CString`\-Objekte als Werte, finden Sie unter [CString Semantics](../atl-mfc-shared/cstring-semantics.md) verwendet.  
  
    > [!NOTE]
    >  Um die Anwendung, damit sie für Unicode oder für ANSI kompiliert werden kann, Codeliteralzeichenfolgen mithilfe des \_T Makros schreiben.  Weitere Informationen finden Sie unter [Unterstützung für Unicode\- und Multibyte\-Zeichensätze \(MBCS\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Zugreifen auf einzelne Zeichen in einem CString  
 Sie können auf einzelne Zeichen in einem `CString`\-Objekt zugreifen, indem Sie die `GetAt` und `SetAt`\-Methoden ausführen.  Sie können das Arrayelement oder Feldindex, Operator \( \[ \] \) auch verwenden anstelle von `GetAt`, um einzelne Zeichen abzurufen.  \(Dies ähnelt dem Zugriff auf Arrayelemente nach Index, wie in den StandardZeichenfolgen im C\-Format.\) Indexwerte für `CString` Zeichen sind nullbasiert.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> Verketten von zwei CString\-Objekten  
 Um zwei `CString`\-Objekte zu verketten, verwenden Sie die Verkettungsoperatoren \(\+ oder \+\=\), wie folgt.  
  
 [!CODE [NVC_ATLMFC_Utilities#185](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#185)]  
  
 Mindestens ein Argument an den Verkettungsoperatoren \(\+ oder \+\=\) ein `CString`\-Objekt, aber Sie sein kann eine konstante Zeichenfolge \(beispielsweise, `"big"`\) oder `char` \(beispielsweise, "x "\) für das andere Argument verwenden.  
  
##  <a name="_core_comparing_cstring_objects"></a> Vergleichen von CString\-Objekten  
 Die Methode und der `Compare` \=\= Operator für `CString` sind gleichwertig.  `Compare`, `operator==` und `CompareNoCase` sind MBCS und Unicode, die Bescheid wissen; `CompareNoCase` ist auch die Groß\-\/Kleinschreibung nicht beachtet.  Die `Collate`\-Methode von `CString` ist gebietsschemaabhängig und ist häufig langsamer als `Compare`.  Verwenden Sie `Collate` nur, in dem Sie durch Sortierregeln bleiben müssen, wie durch das aktuelle Gebietsschema angegeben.  
  
 Die folgende Tabelle zeigt die verfügbaren [CString](../atl-mfc-shared/reference/cstringt-class.md) Vergleichsfunktionen und ihre Funktionen der entsprechend Unicode\/MBCS\-portable in der C\-Laufzeitbibliothek an.  
  
|CString\-Funktion|MBCS\-Funktion|Unicode\-Funktion|  
|-----------------------|--------------------|-----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 Die `CStringT`\-Klassenvorlage definiert die relationalen Operatoren \(\<, \<\=, \>\=, \>, \=\= und\! \=\), die für `CString` verfügbar sind.  Sie können zwei `CStrings` vergleichen, indem Sie diese Operatoren, wie im folgenden Beispiel gezeigt.  
  
 [!CODE [NVC_ATLMFC_Utilities#186](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#186)]  
  
##  <a name="_core_converting_cstring_objects"></a> Konvertieren von CString\-Objekten  
 Informationen zum Konvertieren von CString\-Objekten zu anderen Zeichenfolgentypen, finden Sie unter [Gewusst wie: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md).  
  
## Verwenden CString mit wcout  
 Um ein CString mit `wcout` verwenden müssen Sie das Objekt in `const wchar_t*` wie im folgenden Beispiel gezeigt explizit umwandeln:  
  
```  
CString cs("meow");  
  wcout << (const wchar_t*) cs << endl;  
  
```  
  
 Ohne die Umwandlung wird `cs` behandelt, während `void*` und `wcout` die Adresse des Objekts ausgibt.  Dieses Verhalten wird von kleinere Interaktionen zwischen Vorlagenargumentableitung und Überladungsauflösung verursacht, die in selbst richtig und konform mit dem C\+\+\-Standard sind.  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [Klassenvorlageninstanziierung](../Topic/Class%20Template%20Instantiation.md)   
 [Explizite Spezialisierung von Klassenvorlagen](../Topic/Explicit%20Specialization%20of%20Class%20Templates.md)   
 [Partielle Spezialisierung von Klassenvorlagen](../cpp/template-specialization-cpp.md)   
 [Gewusst wie: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md)