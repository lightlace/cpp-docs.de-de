---
title: time_get_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xloctime/std::time_get_byname
dev_langs:
- C++
helpviewer_keywords:
- time_get_byname class
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: b46b1b88b623c1f1bec315ef2bd488ae3675d0b0
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="timegetbyname-class"></a>time_get_byname-Klasse
Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet vom Typ `time_get`\<CharType, InputIterator> dienen kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Elem, class InputIterator =
    istreambuf_iterator<CharType, char_traits<CharType>>>
class time_get_byname : public time_get<CharType, InputIterator>
{
public:
    explicit time_get_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_get_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_get_byname()
};
```  
  
#### <a name="parameters"></a>Parameter  
 `_Locname`  
 Ein benanntes Gebietsschema.  
  
 `_Refs`  
 Eine initiale Verweisanzahl.  
  
## <a name="requirements"></a>Anforderungen  
 Das Verhalten wird durch das benannte Gebietsschema `_Locname` bestimmt. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [time_get](../standard-library/time-get-class.md#time_get)\<CharType, InputIterator>( `_Refs`).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




