---
title: codecvt_base-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 13cfd32c6df8e191c8329008249cffecdb24e78f
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="codecvtbase-class"></a>codecvt_base-Klasse
Eine Basisklasse für die codecvt-Klasse, die verwendet wird, um einen Enumerationstyp zu definieren, der als **Ergebnis** gekennzeichnet ist. Dieser wird als Rückgabetyp für die Facetmemberfunktionen verwendet, um das Ergebnis einer Konvertierung anzugeben.  
  
## <a name="syntax"></a>Syntax  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
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
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt eine Enumeration, die allen Spezialisierungen der Vorlagenklasse [codecvt](../standard-library/codecvt-class.md) gemein ist. Das Enumerationsergebnis beschreibt die möglichen Rückgabewerte [do_in](../standard-library/codecvt-class.md#do_in) oder [do_out](../standard-library/codecvt-class.md#do_out):  
  
- **ok**, wenn die Konvertierung zwischen internen und externen Zeichencodierungen erfolgreich war.  
  
- **partial**, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.  
  
- **error**, wenn die Quellsequenz fehlerhaft formuliert ist.  
  
- **noconv**, wenn die Funktion keine Konvertierung ausführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




