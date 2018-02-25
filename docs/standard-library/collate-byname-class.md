---
title: collate_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- locale/std::collate_byname
dev_langs:
- C++
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2682abebd6528edbdbec1f6fb1a00082436f1299
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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



