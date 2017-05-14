---
title: ctype_base-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::ctype_base
- ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 74c13251b63018e00490487cb9a45c4bb6d52a21
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="ctypebase-class"></a>ctype_base-Klasse
Die Klasse dient als Basisklasse für Facets der Vorlagenklasse [ctype](../standard-library/ctype-class.md). Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>Hinweise  
 Definiert eine Enumerationsmaske. Jede Enumerationskonstante kennzeichnet eine andere Möglichkeit zum Klassifizieren von Zeichen, wie durch die im Header \<ctype.h> deklarierten Funktionen mit ähnlichen Namen definiert. Folgende Konstanten können verwendet werden:  
  
- **space** ([isspace](../standard-library/locale-functions.md#isspace)-Funktion)  
  
- **print** ([isprint](../standard-library/locale-functions.md#isprint)-Funktion)  
  
- **cntrl** ([iscntrl](../standard-library/locale-functions.md#iscntrl)-Funktion)  
  
- **upper** ([isupper](../standard-library/locale-functions.md#isupper)-Funktion)  
  
- **lower** ([islower](../standard-library/locale-functions.md#islower)-Funktion)  
  
- **digit** ([isdigit](../standard-library/locale-functions.md#isdigit)-Funktion)  
  
- **punct** ([ispunct](../standard-library/locale-functions.md#ispunct)-Funktion)  
  
- **xdigit** ([isxdigit](../standard-library/locale-functions.md#isxdigit)-Funktion)  
  
- **alpha** ([isalpha](../standard-library/locale-functions.md#isalpha)-Funktion)  
  
- **alnum** ([isalnum](../standard-library/locale-functions.md#isalnum)-Funktion)  
  
- **graph** ([isgraph](../standard-library/locale-functions.md#isgraph)-Funktion)  
  
 Eine Kombination von Klassifikationen kann durch Verknüpfen dieser Konstanten mit OR beschrieben werden. Insbesondere trifft **alnum** == ( **alpha**``&#124; **digit**\) and **graph** \=\= \( **alnum**``&#124; **punct**) immer zu.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




