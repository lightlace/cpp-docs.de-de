---
title: "wbuffer_convert-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::cvt::wbuffer_convert"
  - "wbuffer_convert"
  - "stdext.cvt.wbuffer_convert"
  - "cvt.wbuffer_convert"
  - "cvt::wbuffer_convert"
  - "wbuffer/stdext::cvt::wbuffer_convert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wbuffer_convert-Klasse"
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# wbuffer_convert-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Streampuffer, der die Übertragung von Elementen in einen bzw. aus einem Streampuffer steuert.  
  
## Syntax  
  
```  
template<class Codecvt,  
    class Elem = wchar_t,  
    class Traits = std::char_traits<Elem>  
>  
    class wbuffer_convert  
        : public std::basic_streambuf<Elem, Traits>  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Codecvt`|Die [locale](../standard-library/locale-class.md)\-Facet, die das Konvertierungsobjekt darstellt.|  
|`Elem`|Der Breitzeichen\-Elementtyp.|  
|`Traits`|Die mit *Elem* verknüpften Merkmale.|  
  
## Hinweise  
 Die Vorlagenklasse beschreibt einen Streampuffer, der die Übertragung der Elemente des Typs `_Elem` beschreibt, dessen Zeichenmerkmale durch die Klasse `Traits` beschrieben werden, und zwar zu und von einem Bytestreampuffer des Typs `std::streambuf`.  
  
 Konvertierung zwischen einer Sequenz von `Elem`\-Werten und Multibytesequenzen erfolgt durch ein Objekt der Klasse `Codecvt<Elem, char, std::mbstate_t>`, das die Anforderungen des Facets `std::codecvt<Elem, char, std::mbstate_t>` für die Standardcodekonvertierung erfüllt.  
  
 Ein Objekt dieser Vorlagenklasse speichert:  
  
-   Ein Zeiger auf den entsprechenden zugrunde liegenden Bytestreampuffer  
  
-   Ein Zeiger auf das zugeordnete Konvertierungsobjekt \(das freigegeben wird, wenn das [wbuffer\_convert](../standard-library/wbuffer-convert-class.md)\-Objekt gelöscht wird\)  
  
-   Ein Konvertierungszustandsobjekt vom Typ [state\_type](../Topic/wbuffer_convert::state_type.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[wbuffer\_convert](../Topic/wbuffer_convert::wbuffer_convert.md)|Konstruiert ein Objekt vom Typ `wbuffer_convert`.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[state\_type](../Topic/wbuffer_convert::state_type.md)|Ein Typ, der den Konvertierungszustand darstellt.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[rdbuf](../Topic/wbuffer_convert::rdbuf.md)|Gibt den Bytestreampuffer zurück.|  
|[Zustand](../Topic/wbuffer_convert::state.md)|Gibt ein Objekt zurück, das den Zustand für die Konvertierung darstellt.|  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std