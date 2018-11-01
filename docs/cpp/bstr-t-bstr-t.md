---
title: _bstr_t::_bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::_bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
ms.openlocfilehash: 70678b0be8b25bf3ee883630caa26598e5e31089
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450063"
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

*s1*<br/>
Ein `_bstr_t`-Objekt, das kopiert werden soll.

*s2*<br/>
Eine Mehrbytezeichenfolge.

*s3*<br/>
Eine Unicode-Zeichenfolge

*var*<br/>
Ein [_variant_t](../cpp/variant-t-class.md) Objekt.

*BSTR*<br/>
Ein vorhandenes `BSTR`-Objekt.

*fCopy*<br/>
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

[_bstr_t-Klasse](../cpp/bstr-t-class.md)<br/>
[_variant_t-Klasse](../cpp/variant-t-class.md)