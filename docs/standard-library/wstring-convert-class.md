---
title: "wstring_convert-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "cvt.wstring_convert"
  - "wstring_convert"
  - "stdext::cvt::wstring_convert"
  - "cvt::wstring_convert"
  - "wstring/stdext::cvt::wstring_convert"
  - "stdext.cvt.wstring_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wstring_convert-Klasse"
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
caps.latest.revision: 25
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# wstring_convert-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse `wstring_convert` führt Konvertierungen zwischen einer breiten Zeichenfolge und einer Bytezeichenfolge durch.  
  
## Syntax  
  
```  
template<  
    class Codecvt,  
    class Elem = wchar_t  
>  
class wstring_convert  
```  
  
#### Parameter  
 Codecvt  
 Die [locale](../standard-library/locale-class.md)\-Facet, die das Konvertierungsobjekt darstellt.  
  
 Elem  
 Der Breitzeichen\-Elementtyp.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das Konvertierungen zwischen breiten Zeichenfolgenobjekten der Klasse `std::basic_string<Elem>` und Bytezeichenfolgenobjekten der `std::basic_string<char>` \(auch bekannt als `std::string`\) steuert. Die Vorlagenklasse definiert die Typen `wide_string` und `byte_string` als Synonyme für diese beiden Typen. Konvertierung zwischen einer Sequenz von `Elem`\-Werten \(in einem `wide_string`\-Objekt gespeichert\) und Multibytesequenzen \(in einem `byte_string`\-Objekt gespeichert\) erfolgt durch ein Objekt der Klasse `Codecvt<Elem, char, std::mbstate_t>`, das die Anforderungen des Facets `std::codecvt<Elem, char, std::mbstate_t>` für die Standardcodekonvertierung erfüllt.  
  
 Ein Objekt dieser Vorlagenklasse speichert:  
  
-   Eine bei Fehlern anzuzeigende Bytezeichenfolge  
  
-   Eine bei Fehlern anzuzeigende breite Zeichenfolge  
  
-   Ein Zeiger auf das zugeordnete Konvertierungsobjekt \(das freigegeben wird, wenn das wbuffer\_convert\-Objekt gelöscht wird\)  
  
-   Ein Konvertierungszustandsobjekt vom Typ [state\_type](../Topic/wstring_convert::state_type.md)  
  
-   Eine Konvertierungsanzahl  
  
### Konstruktoren  
  
|||  
|-|-|  
|[wstring\_convert](../Topic/wstring_convert::wstring_convert.md)|Konstruiert ein Objekt vom Typ `wstring_convert`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[byte\_string](../Topic/wstring_convert::byte_string.md)|Ein Typ, der eine Bytezeichenfolge darstellt.|  
|[wide\_string](../Topic/wstring_convert::wide_string.md)|Ein Typ, der eine breite Zeichenfolge darstellt.|  
|[state\_type](../Topic/wstring_convert::state_type.md)|Ein Typ, der den Konvertierungszustand darstellt.|  
|[int\_type](../Topic/wstring_convert::int_type.md)|Ein Typ, der eine ganze Zahl darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[from\_bytes](../Topic/wstring_convert::from_bytes.md)|Konvertiert eine Bytezeichenfolge in eine breite Zeichenfolge.|  
|[to\_bytes](../Topic/wstring_convert::to_bytes.md)|Konvertiert eine breite Zeichenfolge in eine Bytezeichenfolge.|  
|[converted](../Topic/wstring_convert::converted.md)|Gibt die Anzahl der erfolgreichen Konvertierungen zurück.|  
|[Zustand](../Topic/wstring_convert::state.md)|Gibt ein Objekt zurück, das den Zustand für die Konvertierung darstellt.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std