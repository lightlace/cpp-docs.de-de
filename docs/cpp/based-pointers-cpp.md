---
title: "Basierte Zeiger (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__based"
  - "__based_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__based-Schlüsselwort [C++]"
  - "Basierte Zeiger"
  - "Zeiger, Basiert"
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Basierte Zeiger (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Das `__based`\-Schlüsselwort ermöglicht das Deklarieren von Zeigern basierend auf Zeigern \(Zeiger, die Offsets von vorhandenen Zeigern sind\).  
  
## Syntax  
  
```  
  
type __based( base ) declarator   
```  
  
## Hinweise  
 Zeiger, die auf Zeigeradressen basieren, sind die einzige Form des `__based`\-Schlüsselworts, das in 32\-Bit\- oder 64\-Bit\-Kompilierungen gültig ist.  Für den 32\-Bit\-C\/C\+\+Compiler von Microsoft ist ein basierter Zeiger ein 32\-Bit\-Offset von einer 32\-Bit\-Zeigerbasis.  Eine ähnliche Einschränkung besteht für 64\-Bit\-Umgebungen, in denen ein basierter Zeiger ein 64\-Bit\-Offset von der 64\-Bit\-Basis ist.  
  
 Eine Verwendung von Zeigern, die auf Zeigern basieren, ist für dauerhafte Bezeichner, die Zeiger enthalten.  Eine verknüpfte Liste, die aus Zeigern auf Grundlage eines Zeigers besteht, kann auf Datenträger gespeichert werden, dann an eine andere Stelle im Arbeitsspeicher neu geladen werden, wobei die Zeiger weiterhin gültig bleiben.  Beispiel:  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Dem Zeiger `vpBuffer` wird die Adresse des später im Programm zugewiesenen Arbeitsspeichers zugeteilt.  Die verknüpfte Liste wird relativ zum Wert von `vpBuffer` verschoben.  
  
> [!NOTE]
>  Das Beibehalten von Bezeichnern, die Zeiger enthalten, kann auch erzielt werden, indem [Speicherabbilddateien](http://msdn.microsoft.com/library/windows/desktop/aa366556) verwendet werden.  
  
 Beim Dereferenzieren eines basierten Zeigers muss die Basis explizit angegeben werden oder implizit durch die Deklaration bekannt sein.  
  
 Aus Gründen der Kompatibilität mit früheren Versionen ist **\_based** ein Synonym für `__based`.  
  
## Beispiel  
 Im folgenden Code wird gezeigt, wie ein Basiszeiger verändert wird, indem seine Basis geändert wird.  
  
```  
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
  **1**  
**2**  
**10**  
**11**   
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [alloc\_text](../preprocessor/alloc-text.md)