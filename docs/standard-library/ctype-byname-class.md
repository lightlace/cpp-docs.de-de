---
title: ctype_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::ctype_byname
dev_langs:
- C++
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 5f57ef8eadf5ea963ef4a8b8c1eaa7b6ec48ee6d
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ctypebyname-class"></a>ctype_byname-Klasse
Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als ctype-Facet eines angegebenen Gebietsschemas dienen kann und die Klassifizierung von Zeichen sowie die Konvertierung von Zeichen zwischen Groß-/Kleinschreibung und zwischen nativen und gebietsschemaspezifischen Zeichensätzen ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```  
  
## <a name="remarks"></a>Hinweise  
 Das Verhalten wird durch das benannte Gebietsschema `_Locname` bestimmt. Jeder Konstruktor initialisiert sein Basisobjekt mit [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) oder der jeweiligen Entsprechung für die Basisklasse `ctype<char>`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




