---
title: _bstr_t::_bstr_t | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba2935dcec7863e43c0dd6a0a4e55ee5c4f3d28d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401645"
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
 *s1*  
 Ein `_bstr_t`-Objekt, das kopiert werden soll.  
  
 *s2*  
 Eine Mehrbytezeichenfolge.  
  
 *s3*  
 Eine Unicode-Zeichenfolge  
  
 *var*  
 Ein [_variant_t](../cpp/variant-t-class.md) Objekt.  
  
 *BSTR*  
 Ein vorhandenes `BSTR`-Objekt.  
  
 *fCopy*  
 False gibt an, die *Bstr* Argument in das neue Objekt angefügt, ohne dass eine Kopie durch den Aufruf `SysAllocString`.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle werden die `_bstr_t`-Konstruktoren beschrieben.  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`_bstr_t( )`|Erstellt ein standardmäßiges `_bstr_t` -Objekt, ein NULL-Wert kapselt `BSTR` Objekt.|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|Erstellt ein `_bstr_t`-Objekt als Kopie eines anderen.<br /><br /> Dies ist eine *flache* Kopie, die inkrementiert den Verweiszähler des gekapselten `BSTR` Objekt statt einen neuen zu erstellen.|  
|`_bstr_t( char*`  `s2`  `)`|Erstellt ein `_bstr_t`-Objekt durch Aufrufen von `SysAllocString`, um ein neues `BSTR`-Objekt zu erstellen und es dann zu kapseln.<br /><br /> Dieser Konstruktor führt zuerst eine Konvertierung von Multibyte in Unicode aus.|  
|`_bstr_t( wchar_t*`  `s3`  `)`|Erstellt ein `_bstr_t`-Objekt durch Aufrufen von `SysAllocString`, um ein neues `BSTR`-Objekt zu erstellen und es dann zu kapseln.|  
|`_bstr_t( _variant_t&`  `var`  `)`|Erstellt ein `_bstr_t`-Objekt aus einem `_variant_t`-Objekt, indem zunächst ein `BSTR`-Objekt aus dem gekapselten VARIANT-Objekt abgerufen wird.|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|Erstellt ein `_bstr_t`-Objekt aus einem vorhandenen `BSTR` (im Gegensatz zu einer `wchar_t*`-Zeichenfolge). Wenn *fCopy* ist "false", dem angegebenen `BSTR` auf das neue Objekt angefügt, ohne dass eine neue Kopie mit `SysAllocString`.<br /><br /> Dieser Konstruktor wird von Wrapperfunktionen in Typbibliothekheadern verwendet, um den von einer Schnittstellenmethode zurückgegebenen `BSTR` zu kapseln und dessen Besitz zu übernehmen.|  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)   
 [_variant_t-Klasse](../cpp/variant-t-class.md)