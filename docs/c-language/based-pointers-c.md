---
title: "Basierte Zeiger (C)"
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
  - "C"
helpviewer_keywords: 
  - "__based-Schlüsselwort [C]"
  - "Basierende Adressierung"
  - "Basierte Zeiger"
  - "Zeiger, Basiert"
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Basierte Zeiger (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 [\_\_based \(C\+\+\-Verweis\)](../cpp/based-pointers-cpp.md)  
  
 Für die 32\-Bit\- und 64\-Bit\-C\-Compiler von Microsoft ist ein basierter Zeiger ein 32\-Bit\- oder 64\-Bit\-Offset einer 32\-Bit\- oder 64\-Bit\-Zeigerbasis.  Die basierende Adressierung eignet sich zur Ausübung der Kontrolle über Abschnitte, denen Objekte zugeordnet sind; dadurch werden die Größe der ausführbaren Datei verringert und die Ausführungsgeschwindigkeit erhöht.  Im Allgemeinen ist die Form zum Angeben eines basierten Zeigers  
  
```  
  
type __based( base ) declarator   
```  
  
 Die "basierend auf Zeiger"\-Variante der basierenden Adressierung ermöglicht die Angabe eines Zeigers als Basis.  Der basierte Zeiger ist dann ein Offset im Arbeitsspeicherbereich, der am Anfang des Zeigers beginnt, auf dem er basiert.  Zeiger, die auf Zeigeradressen basieren, sind die einzige Form des `__based`\-Schlüsselworts, das in 32\-Bit\- und 64\-Bit\-Kompilierungen gültig ist.  In solchen Kompilierungen sind sie 32\-Bit\- oder 64\-Bit\-Verschiebungen von einer 32\-Bit\- oder 64\-Bit\-Basis.  
  
 Eine Verwendung von Zeigern, die auf Zeigern basieren, ist für dauerhafte Bezeichner, die Zeiger enthalten.  Eine verknüpfte Liste, die aus Zeigern auf Grundlage eines Zeigers besteht, kann auf Datenträger gespeichert werden, dann an eine andere Stelle im Arbeitsspeicher neu geladen werden, wobei die Zeiger weiterhin gültig bleiben.  
  
 Das folgende Beispiel zeigt einen Zeiger, der auf einem Zeiger basiert.  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Dem Zeiger `vpBuffer` wird die Adresse des später im Programm zugewiesenen Arbeitsspeichers zugeteilt.  Die verknüpfte Liste wird relativ zum Wert von `vpBuffer` verschoben.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Deklaratoren und Variablendeklarationen](../c-language/declarators-and-variable-declarations.md)