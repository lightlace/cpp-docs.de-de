---
title: "Programmieren mit CComBSTR (ATL)"
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
  - "CComBSTR-Klasse, Programmieren mit"
  - "Unicode, Verwenden von CComBSTR [ATL]"
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Programmieren mit CComBSTR (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die ATL\-Klasse [CComBSTR](../atl/reference/ccombstr-class.md) stellt einen Wrapper um den `BSTR` Datentyp bereit.  Während `CComBSTR` ein nützliches Tool ist, gibt es einige Situationen, die Vorsicht erfordern.  
  
-   [Konvertierungsprobleme](#programmingwithccombstr_conversionissues)  
  
-   [Bereichs\-Probleme](#programmingwithccombstr_scopeissues)  
  
-   [Das CComBSTR\-Objekt explizit freigeben](#programmingwithccombstr_explicitlyfreeing)  
  
-   [Verwenden CComBSTR\-Objekte in\-Schleifen](#programmingwithccombstr_usingloops)  
  
-   [Speicherverlust\-Probleme](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a> Konvertierungsprobleme  
 Obwohl einige `CComBSTR`\-Methoden automatisch ein ANSI\-Zeichenfolgenargument in Unicode konvertieren, geben die Methoden immer Unicode\-Formatzeichenfolgen zurück.  Um die Ausgabezeichenfolge zurück in ANSI zu konvertieren, verwenden Sie eine ATL\-Konvertierungsklasse.  Weitere Informationen über die ATL\-Konvertierungsklassen, finden Sie unter [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
### Beispiel  
 [!CODE [NVC_ATL_Utilities#114](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#114)]  
  
 Wenn Sie ein Zeichenfolgenliteral verwenden, um ein `CComBSTR`\-Objekt zu ändern, verwenden Sie Breitzeichen\-Zeichenfolgen.  Dies reduziert unnötige Konvertierungen.  
  
### Beispiel  
 [!CODE [NVC_ATL_Utilities#115](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#115)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a> Bereichs\-Probleme  
 Wie bei allen gut konzipierte Klasse, gibt `CComBSTR` seine Ressourcen frei, wenn sie den Gültigkeitsbereich verlässt.  Wenn eine Funktion einen Zeiger auf die `CComBSTR` Zeichenfolge zurückgibt, kann diese Probleme verursachen, da der Zeiger Arbeitsspeicher verweist, der bereits freigegeben ist.  In diesen Fällen verwenden Sie die Methode **Copy**, wie unten dargestellt.  
  
### Beispiel  
 [!CODE [NVC_ATL_Utilities#116](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#116)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a> Das CComBSTR\-Objekt explizit freigeben  
 Es ist möglich, die Zeichenfolge explizit freizugeben, die im `CComBSTR`\-Objekt enthalten ist, bevor das Objekt Gültigkeitsbereich verlässt.  Wenn die Zeichenfolge verworfen wird, ist das Objekt `CComBSTR` ungültig.  
  
### Beispiel  
 [!CODE [NVC_ATL_Utilities#117](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#117)]  
  
##  <a name="programmingwithccombstr_usingloops"></a> Verwenden CComBSTR\-Objekte in\-Schleifen  
 Da die `CComBSTR`\-Klasse einen Puffer erfolgt, um bestimmte Vorgänge, wie der `+=`\-Operator oder die **Append**\-Methode auszuführen, wird es nicht empfohlen, Zeichenfolgenbearbeitung innerhalb einer kurzen Schleife ausführen.  In diesen Situationen stellt `CStringT` eine bessere Leistung.  
  
### Beispiel  
 [!CODE [NVC_ATL_Utilities#118](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#118)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a> Speicherverlust\-Probleme  
 Die Übergabe der Adresse von initialisierten `CComBSTR` zu einer Funktion als **\[out\]**\-Parameter verursacht einen Speicherverlust.  
  
 Im Beispiel unten, wird die Zeichenfolge, die zugeordnet ist, um die Zeichenfolge `"Initialized"` anzuhalten, verloren geht, wenn die Funktion `MyGoodFunction` die Zeichenfolge ersetzt.  
  
 [!CODE [NVC_ATL_Utilities#119](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#119)]  
  
 Um den Verlust zu vermeiden, rufen Sie die Methode **Empty** auf vorhandene `CComBSTR`\-Objekten auf bevor Sie die Adresse als **\[out\]**\-Parameter übergeben.  
  
 Beachten Sie, dass der gleiche Code ohne Datenverlust führen würde, wenn der Parameter der Funktion **\[in, out\]** war.  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../Topic/wstring.md)   
 [String Conversion Macros](../atl/reference/string-conversion-macros.md)