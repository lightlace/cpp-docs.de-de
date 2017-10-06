---
title: _bstr_t::_bstr_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::_bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
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
ms.openlocfilehash: ccf087d3b48a00de00eab7016563f59d4ad2d974
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t
**Microsoft-spezifisch**  
  
 Erstellt ein `_bstr_t`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `s1`  
 Ein `_bstr_t`-Objekt, das kopiert werden soll.  
  
 `s2`  
 Eine Mehrbytezeichenfolge.  
  
 `s3`  
 Eine Unicode-Zeichenfolge  
  
 `var`  
 Ein [_variant_t](../cpp/variant-t-class.md) Objekt.  
  
 `bstr`  
 Ein vorhandenes `BSTR`-Objekt.  
  
 `fCopy`  
 Wenn `false`, wird das `bstr`-Argument an das neue Objekt angefügt, ohne dass durch Aufruf von `SysAllocString` eine Kopie erstellt wird.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle werden die `_bstr_t`-Konstruktoren beschrieben.  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`_bstr_t( )`|Erstellt ein standardmäßiges `_bstr_t` Objekt, das einen NULL-Wert kapselt `BSTR` Objekt.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Erstellt ein `_bstr_t`-Objekt als Kopie eines anderen.<br /><br /> Dies ist eine *flache* Kopie, die inkrementiert den Verweiszähler des gekapselten `BSTR` Objekt, anstatt ein neue zu erstellen.|  
|`_bstr_t( char*`  `s2`  `)`|Erstellt ein `_bstr_t`-Objekt durch Aufrufen von `SysAllocString`, um ein neues `BSTR`-Objekt zu erstellen und es dann zu kapseln.<br /><br /> Dieser Konstruktor führt zuerst eine Konvertierung von Multibyte in Unicode aus.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Erstellt ein `_bstr_t`-Objekt durch Aufrufen von `SysAllocString`, um ein neues `BSTR`-Objekt zu erstellen und es dann zu kapseln.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Erstellt ein `_bstr_t`-Objekt aus einem `_variant_t`-Objekt, indem zunächst ein `BSTR`-Objekt aus dem gekapselten VARIANT-Objekt abgerufen wird.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Erstellt ein `_bstr_t`-Objekt aus einem vorhandenen `BSTR` (im Gegensatz zu einer `wchar_t*`-Zeichenfolge). Wenn `fCopy` False ist, wird das bereitgestellte `BSTR` an das neue Objekt angefügt, ohne dass eine neue Kopie mit `SysAllocString` erstellt wird.<br /><br /> Dieser Konstruktor wird von Wrapperfunktionen in Typbibliothekheadern verwendet, um den von einer Schnittstellenmethode zurückgegebenen `BSTR` zu kapseln und dessen Besitz zu übernehmen.|  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)   
 [_variant_t-Klasse](../cpp/variant-t-class.md)
