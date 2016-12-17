---
title: "time_base-Klasse"
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
  - "std.time_base"
  - "std::time_base"
  - "time_base"
  - "locale/std::time_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_base-Klasse"
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# time_base-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klasse dient als Basisklasse für die Aspekte von time\_get Vorlagenklasse und definiert nur den enumerierten **dateorder** und mehrere Konstanten aus dieses Typs.  
  
## Syntax  
  
```  
class time_base : public locale::facet {  
public:  
    enum dateorder {no_order, dmy, mdy, ymd, ydm};  
    time_base(  
        size_t _Refs = 0  
    )  
    ~time_base();  
};  
```  
  
## Hinweise  
 Jede Konstante kennzeichnet eine andere Weise, die Komponenten eines Datums zu sortieren.  Die Konstanten sind:  
  
-   **no\_order** gibt keine bestimmten Reihenfolge.  
  
-   **dmy** gibt den Reihenfolgentag, Monat, Jahr dann, wie in am 2. Dezember 1979 an.  
  
-   **mdy** gibt den Reihenfolgenmonat, Tag, dann Jahr, wie in am 2. Dezember 1979 an.  
  
-   **ymd** gibt den Reihenfolgenjahr, Monat, Tag, dann als \/2. im Jahre 1979 \/12 an.  
  
-   **ydm** gibt den Reihenfolgenjahr, Tag, Monat, dann als im Jahre 1979 an: Am 2. Dezember  
  
## Anforderungen  
 **Header:** \<Gebietsschema\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)