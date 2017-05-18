---
title: numpunct_byname-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- numpunct_byname
- xlocnum/std::numpunct_byname
dev_langs:
- C++
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 1821793921924a5f0bb75703f581705f7f1d8115
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="numpunctbyname-class"></a>numpunct_byname-Klasse
Die abgeleitete Vorlagenklasse beschreibt ein Objekt, das als `numpunct`-Facet eines angegebenen Gebietsschemas dienen kann und die Formatierung und Interpunktion von numerischen und booleschen Ausdrücken ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

 };
```  
  
## <a name="remarks"></a>Hinweise  
 Sein Verhalten wird durch das [benannte](../standard-library/locale-class.md#name) Gebietsschema `_Locname` bestimmt. Der Konstruktor initialisiert sein Basisobjekt mit [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>(`_Refs`).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)




