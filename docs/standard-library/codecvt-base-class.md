---
title: "codecvt_base-Klasse"
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
  - "codecvt_base"
  - "xlocale/std::codecvt_base"
  - "std.codecvt_base"
  - "std::codecvt_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_base-Klasse"
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Basisklasse für die codecvt Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als **Ergebnis** gekennzeichnet ist, verwendet wie der Rückgabetyp, damit die Facetmemberfunktionen dem Ergebnis einer Konvertierung angeben.  
  
## Syntax  
  
```  
class codecvt_base : public locale::facet {  
public:  
    enum result {ok, partial, error, noconv};  
    codecvt_base(  
        size_t _Refs = 0  
);  
    bool always_noconv() const;  
    int max_length() const;  
    int encoding() const;  
    ~codecvt_base()  
protected:  
    virtual bool do_always_noconv() const;  
    virtual int do_max_length() const;  
    virtual int do_encoding() const;  
};  
```  
  
## Hinweise  
 Die Klasse beschreibt ein Enumerationscommon auf alle Spezialisierungen der Vorlagenklasse [codecvt](../standard-library/codecvt-class.md).  Das Enumerationsergebnis werden die möglichen Werte von [do\_in](../Topic/codecvt::do_in.md) oder [do\_out](../Topic/codecvt::do_out.md):  
  
-   **OK**, wenn die Konvertierung zwischen den internen und externen Zeichencodierungen folgt.  
  
-   **partial**, wenn das Ziel nicht groß genug ist, sodass die Konvertierung erfolgreich ausgeführt.  
  
-   **Fehler**, wenn die Quellsequenz nicht ordnungsgemäß formatiert ist.  
  
-   **noconv**, wenn die Funktion keine Konvertierung ausgeführt wird.  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)