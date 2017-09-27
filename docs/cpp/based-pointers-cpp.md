---
title: Basierte Zeiger (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __based
- __based_cpp
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: f3ba9e269a01fb4c10cce9417032ec47c1b3c158
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="based-pointers-c"></a>Basierte Zeiger (C++)
**Microsoft-spezifisch**  
  
 Das `__based`-Schlüsselwort ermöglicht das Deklarieren von Zeigern basierend auf Zeigern (Zeiger, die Offsets von vorhandenen Zeigern sind).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
type __based( base ) declarator   
```  
  
## <a name="remarks"></a>Hinweise  
 Zeiger, die auf Zeigeradressen basieren, sind die einzige Form des `__based`-Schlüsselworts, das in 32-Bit- oder 64-Bit-Kompilierungen gültig ist. Für den 32-Bit-C/C++Compiler von Microsoft ist ein basierter Zeiger ein 32-Bit-Offset von einer 32-Bit-Zeigerbasis. Eine ähnliche Einschränkung besteht für 64-Bit-Umgebungen, in denen ein basierter Zeiger ein 64-Bit-Offset von der 64-Bit-Basis ist.  
  
 Eine Verwendung von Zeigern, die auf Zeigern basieren, ist für dauerhafte Bezeichner, die Zeiger enthalten. Eine verknüpfte Liste, die aus Zeigern auf Grundlage eines Zeigers besteht, kann auf Datenträger gespeichert werden, dann an eine andere Stelle im Arbeitsspeicher neu geladen werden, wobei die Zeiger weiterhin gültig bleiben. Zum Beispiel:  
  
```  
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Dem Zeiger `vpBuffer` wird die Adresse des später im Programm zugewiesenen Arbeitsspeichers zugeteilt. Die verknüpfte Liste wird relativ zum Wert von `vpBuffer` verschoben.  
  
> [!NOTE]
>  Beibehalten von Bezeichnern, die Zeiger können auch vorgenommen werden, indem Sie mit [Speicherabbilddateien](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Beim Dereferenzieren eines basierten Zeigers muss die Basis explizit angegeben werden oder implizit durch die Deklaration bekannt sein.  
  
 Um die Kompatibilität mit früheren Versionen **_based** ist ein Synonym für `__based`.  
  
## <a name="example"></a>Beispiel  
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
  
```Output  
1  
2  
10  
11  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [alloc_text](../preprocessor/alloc-text.md)
