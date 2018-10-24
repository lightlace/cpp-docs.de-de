---
title: _variant_t::_variant_t | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c3b1bb7d345d87e4f592dc82971f1efe86dd9a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079582"
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t

**Microsoft-spezifisch**

Erstellt ein `_variant_t`-Objekt.

## <a name="syntax"></a>Syntax

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>Parameter

*varSrc*<br/>
Ein `VARIANT`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.

*pVarSrc*<br/>
Zeiger auf eine `VARIANT` Objekt, das in die neue kopiert werden `_variant_t` Objekt.

*var_t_Src*<br/>
Ein `_variant_t`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.

*fCopy*<br/>
Wenn **"false"**, dem angegebenen `VARIANT` auf das neue Objekt angefügt ist `_variant_t` Objekt, ohne dass eine neue Kopie von `VariantCopy`.

*ISrc, sSrc*<br/>
Ein ganzer Wert, der in das neue `_variant_t` -Objekt kopiert werden soll.

*vtSrc*<br/>
Die `VARTYPE` für das neue `_variant_t` Objekt.

*fltSrc, dblSrc*<br/>
Ein in das neue `_variant_t`-Objekt zu kopierender numerischer Wert.

*cySrc*<br/>
Ein `CY`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.

*bstrSrc*<br/>
Ein `_bstr_t`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.

*strSrc, wstrSrc*<br/>
Eine Zeichenfolge, die in das neue `_variant_t`-Objekt kopiert werden soll.

*bSrc*<br/>
Ein **"bool"** Wert in die neue kopiert werden `_variant_t` Objekt.

*pIUknownSrc*<br/>
COM-Schnittstellenzeiger auf ein Objekt "VT_UNKNOWN" gekapselt werden, in das neue `_variant_t` Objekt.

*pDispSrc*<br/>
COM-Schnittstellenzeiger auf ein Objekt "VT_DISPATCH" gekapselt werden, in das neue `_variant_t` Objekt.

*decSrc*<br/>
Ein `DECIMAL`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.

*bSrc*<br/>
Ein `BYTE`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.

*cSrc*<br/>
Ein **Char** Wert in die neue kopiert werden `_variant_t` Objekt.

*usSrc*<br/>
Ein **unsigned short** Wert in die neue kopiert werden `_variant_t` Objekt.

*ulSrc*<br/>
Ein **unsigned long** Wert in die neue kopiert werden `_variant_t` Objekt.

*iSrc*<br/>
Ein **Int** Wert in die neue kopiert werden `_variant_t` Objekt.

*uiSrc*<br/>
Ein **ganze Zahl ohne Vorzeichen** Wert in die neue kopiert werden `_variant_t` Objekt.

*i8Src*<br/>
Ein **__int64** Wert in die neue kopiert werden `_variant_t` Objekt.

*ui8Src*<br/>
Ein **__int64 ohne Vorzeichen** Wert in die neue kopiert werden `_variant_t` Objekt.

## <a name="remarks"></a>Hinweise

- **_variant_t ()** erstellt ein leeres `_variant_t` Objekt `VT_EMPTY`.

- **_variant_t (VARIANT &**  *VarSrc*  **)** erstellt eine `_variant_t` Objekt aus einer Kopie der `VARIANT` Objekt.     Der Varianttyp wird beibehalten.

- **_variant_t (VARIANT**<strong>\*</strong>*pVarSrc*  **)** erstellt eine `_variant_t` Objekt aus einer Kopie der `VARIANT` Objekt.     Der Varianttyp wird beibehalten.

- **_variant_t (_variant_t &***Var_t_Src***)** erstellt eine `_variant_t` Objekt von einem anderen `_variant_t` Objekt.     Der Varianttyp wird beibehalten.

- **_variant_t (VARIANT &**  *VarSrc* **, "bool"**`fCopy`**)** erstellt eine `_variant_t` -Objekt aus einem vorhandenen `VARIANT` -Objekt.       Wenn *fCopy* ist **"false"**, **VARIANT** Objekt ist auf das neue Objekt angefügt, ohne dass eine Kopie.

- **_variant_t (short**  *sSrc* **, VARTYPE**  `vtSrc`  **= VT_I2)** erstellt eine `_variant_t` Objekt des Typs, die von einem VT_I2oderVT_BOOL**kurze** Integer-Wert. Alle anderen `VARTYPE` führt zu einem Fehler E_INVALIDARG zurückgegeben.

- **_variant_t (long** `lSrc` **, VARTYPE**`vtSrc`**= VT_I4)** erstellt eine `_variant_t` Objekt des Typs VT_I4, VT_BOOL oder VT_ERROR aus einer **lange**  Integer-Wert.       Alle anderen `VARTYPE` führt zu einem Fehler E_INVALIDARG zurückgegeben.

- **_variant_t (Float**`fltSrc`**)** erstellt eine `_variant_t` Objekt des Typs VT_R4 aus einer **"float"** numerischer Wert.    

- **_variant_t (double** `dblSrc` **, VARTYPE**`vtSrc`**= VT_R8)** erstellt eine `_variant_t` Objekt vom Typ VT_R8 oder VT_DATE aus einem **Double** numerischer Wert.       Alle anderen `VARTYPE` führt zu einem Fehler E_INVALIDARG zurückgegeben.

- **_variant_t (CY &**`cySrc`**)** erstellt eine `_variant_t` Objekt des Typs VT_CY aus einem `CY` Objekt.    

- **_variant_t (_bstr_t &**`bstrSrc`**)** erstellt eine `_variant_t` Objekt vom Typ VT_BSTR aus einem `_bstr_t` Objekt.     Ein neues `BSTR` wird zugeordnet.

- **_variant_t (Wchar_t** <strong>\*</strong> *WstrSrc*  **)** erstellt eine `_variant_t` Objekt vom Typ "VT_BSTR" von Unicode-Zeichenfolge.   Ein neues `BSTR` wird zugeordnet.

- **_variant_t (Char**<strong>\*</strong>  `strSrc`  **)** erstellt eine `_variant_t` Objekt vom Typ VT_BSTR aus einer Zeichenfolge. Ein neues `BSTR` wird zugeordnet.

- **_variant_t (Bool**`bSrc`**)** erstellt eine `_variant_t` Objekt des Typs VT_BOOL aus einer **"bool"** Wert.    

- **_variant_t (IUnknown**<strong>\*</strong>  `pIUknownSrc` **, "bool"**  `fAddRef`**= True)** erstellt eine `_variant_t` Objekt des Typs VT_UNKNOWN aus einem COM-Schnittstellenzeiger. Wenn `fAddRef` ist **"true"**, klicken Sie dann `AddRef` für den bereitgestellten Schnittstellenzeiger auf den Aufruf von entsprechend aufgerufen wird `Release` erfolgt, die bei der `_variant_t` -Objekt zerstört wird. Es liegt bei Ihnen Aufrufen `Release` auf den bereitgestellten Schnittstellenzeiger auf. Wenn `fAddRef` ist **"false"**, übernimmt dieser Konstruktor den Besitz des angegebenen Schnittstellenzeigers, rufen Sie keine `Release` auf den bereitgestellten Schnittstellenzeiger auf.

- **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc` **, "bool"**`fAddRef`**= True)** erstellt eine `_variant_t` Objekt Geben Sie "VT_DISPATCH" aus einem COM-Schnittstellenzeiger.       Wenn `fAddRef` ist **"true"**, klicken Sie dann `AddRef` für den bereitgestellten Schnittstellenzeiger auf den Aufruf von entsprechend aufgerufen wird `Release` erfolgt, die bei der `_variant_t` -Objekt zerstört wird. Es liegt bei Ihnen Aufrufen `Release` auf den bereitgestellten Schnittstellenzeiger auf. Wenn `fAddRef` ist **"false"**, übernimmt dieser Konstruktor den Besitz des angegebenen Schnittstellenzeigers, rufen Sie keine `Release` auf den bereitgestellten Schnittstellenzeiger auf.

- **_variant_t (DECIMAL &**`decSrc`**)** erstellt eine `_variant_t` Objekt des Typs VT_DECIMAL aus einem `DECIMAL` Wert.    

- **_variant_t (BYTE**`bSrc`**)** erstellt eine `_variant_t` Objekt des Typs `VT_UI1` aus einem `BYTE` Wert.    

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)