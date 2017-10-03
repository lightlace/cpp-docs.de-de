---
title: moneypunct_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::moneypunct_byname
dev_langs:
- C++
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
caps.latest.revision: 22
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
ms.openlocfilehash: b13028649eeccad5fbc832098a3b070bb81dad45
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="moneypunctbyname-class"></a>moneypunct_byname-Klasse
Eine abgeleitete Vorlagenklasse, die ein Objekt beschreibt, das als `moneypunct`-Facet eines bestimmten Gebietsschemas dienen kann und die Formatierung von monetären Ein- und Ausgabefeldern ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```  
  
## <a name="remarks"></a>Hinweise  
 Das Verhalten wird durch das benannte Gebietsschema `_Locname` bestimmt. Alle Konstruktoren initialisieren ihr jeweiliges Basisobjekt mit [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl>( `_Refs`).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




