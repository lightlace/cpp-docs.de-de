---
title: collate_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 24
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
ms.openlocfilehash: 8cb03c73fca3c2076655d8a6d93de9f215cc6dfc
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="collatebyname-class"></a>collate_byname-Klasse
Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als Sortierungsfacet eines angegebenen Gebietsschemas dienen kann, sodass für einen kulturellen Bereich spezifische Informationen über Konventionen zum Sortieren von Zeichenfolgen abgerufen werden können.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>Parameter  
 `_Locname`  
 Ein benanntes Gebietsschema.  
  
 `_Refs`  
 Eine initiale Verweisanzahl.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das als [Gebietsschemafacet](../standard-library/locale-class.md#facet_class) des Typs [collate](../standard-library/collate-class.md#collate)\<CharType> dienen kann. Sein Verhalten wird durch das [benannte](../standard-library/locale-class.md#name) Gebietsschema `_Locname` bestimmt. Jeder Konstruktor initialisiert sein Basisobjekt mit [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




