---
title: _variant_t::_variant_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd85a54e9f73352894f6575051fe1ea8be0698fb
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
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
 *varSrc*  
 Ein **VARIANT** -Objekt, in das neue kopiert werden `_variant_t` Objekt.  
  
 *pVarSrc*  
 Zeiger auf eine **VARIANT** -Objekt, in das neue kopiert werden `_variant_t` Objekt.  
  
 *var_t_Src*  
 Ein `_variant_t`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 `fCopy`  
 Wenn "false", dem angegebenen **VARIANT** auf das neue Objekt angefügt ist `_variant_t` Objekt, ohne dass eine neue Kopie von **VariantCopy**.  
  
 *ISrc, sSrc*  
 Ein ganzer Wert, der in das neue `_variant_t` -Objekt kopiert werden soll.  
  
 `vtSrc`  
 Die **VARTYPE** für die neue `_variant_t` Objekt.  
  
 *fltSrc, dblSrc*  
 Ein in das neue `_variant_t`-Objekt zu kopierender numerischer Wert.  
  
 `cySrc`  
 Ein **CY** -Objekt, in das neue kopiert werden `_variant_t` Objekt.  
  
 `bstrSrc`  
 Ein `_bstr_t`-Objekt, das in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 *strSrc, wstrSrc*  
 Eine Zeichenfolge, die in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 `bSrc`  
 Ein `bool`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 `pIUknownSrc`  
 COM-Schnittstellenzeiger auf eine **VT_UNKNOWN** -Objekt, in das neue gekapselt werden `_variant_t` Objekt.  
  
 `pDispSrc`  
 COM-Schnittstellenzeiger auf eine **VT_DISPATCH** -Objekt, in das neue gekapselt werden `_variant_t` Objekt.  
  
 `decSrc`  
 Ein **DECIMAL** Wert an, in das neue kopiert werden `_variant_t` Objekt.  
  
 `bSrc`  
 Ein **BYTE** Wert an, in das neue kopiert werden `_variant_t` Objekt.  
  
 `cSrc`  
 Ein `char`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 *usSrc*  
 Ein **kurz ohne Vorzeichen** Wert an, in das neue kopiert werden `_variant_t` Objekt.  
  
 *ulSrc*  
 Ein `unsigned long`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 `iSrc`  
 Ein `int`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 *uiSrc*  
 Ein `unsigned int`-Wert, der in das neue `_variant_t`-Objekt kopiert werden soll.  
  
 *i8Src*  
 Ein __**int64** Wert an, in das neue kopiert werden `_variant_t` Objekt.  
  
 *ui8Src*  
 Ein **unsigned __int64** Wert an, in das neue kopiert werden `_variant_t` Objekt.  
  
## <a name="remarks"></a>Hinweise  
  
-   **_variant_t ()** erstellt ein leeres `_variant_t` Objekt `VT_EMPTY`.  
  
-   **_variant_t( VARIANT&**  *varSrc*  **)** Constructs a `_variant_t` object from a copy of the **VARIANT** object. Der Varianttyp wird beibehalten.  
  
-   **_variant_t( VARIANT\***  *pVarSrc*  **)** Constructs a `_variant_t` object from a copy of the **VARIANT** object. Der Varianttyp wird beibehalten.  
  
-   **_variant_t( _variant_t&**  *var_t_Src*  **)** Constructs a `_variant_t` object from another `_variant_t` object. Der Varianttyp wird beibehalten.  
  
-   **_variant_t( VARIANT&**  *varSrc* **, bool**  `fCopy`  **)** Constructs a `_variant_t` object from an existing **VARIANT** object. Wenn `fCopy` ist **"false"**, **VARIANT** Objekt in das neue Objekt angefügt, ohne dass eine Kopie.  
  
-   **_variant_t( short**  *sSrc* **, VARTYPE**  `vtSrc`  **= VT_I2 )** Constructs a `_variant_t` object of type `VT_I2` or `VT_BOOL` from a **short** integer value. Alle anderen **VARTYPE** führt zu einem `E_INVALIDARG` Fehler.  
  
-   **_variant_t( long**  `lSrc` **, VARTYPE**  `vtSrc`  **= VT_I4 )** Constructs a `_variant_t` object of type `VT_I4`, `VT_BOOL`, or `VT_ERROR` from a **long** integer value. Alle anderen **VARTYPE** führt zu einem `E_INVALIDARG` Fehler.  
  
-   **_variant_t( float**  `fltSrc`  **)** Constructs a `_variant_t` object of type `VT_R4` from a **float** numerical value.  
  
-   **_variant_t( double**  `dblSrc` **, VARTYPE**  `vtSrc`  **= VT_R8 )** Constructs a `_variant_t` object of type `VT_R8` or `VT_DATE` from a **double** numerical value. Alle anderen **VARTYPE** führt zu einem `E_INVALIDARG` Fehler.  
  
-   **_variant_t( CY&**  `cySrc`  **)** Constructs a `_variant_t` object of type `VT_CY` from a **CY** object.  
  
-   **_variant_t( _bstr_t&**  `bstrSrc`  **)** Constructs a `_variant_t` object of type `VT_BSTR` from a `_bstr_t` object. Ein neues `BSTR` wird zugeordnet.  
  
-   **_variant_t (Wchar_t \***  *WstrSrc***)** erstellt eine `_variant_t` Objekt des Typs `VT_BSTR` eine Unicode-Zeichenfolge.   Ein neues `BSTR` wird zugeordnet.  
  
-   **_variant_t( char\***  `strSrc`  **)** Constructs a `_variant_t` object of type `VT_BSTR` from a string. Ein neues `BSTR` wird zugeordnet.  
  
-   **_variant_t( bool**  `bSrc`  **)** Constructs a `_variant_t` object of type `VT_BOOL` from a `bool` value.  
  
-   **_variant_t( IUnknown\***  `pIUknownSrc` **, bool**  `fAddRef`  **= true )** Constructs a `_variant_t` object of type **VT_UNKNOWN** from a COM interface pointer. Wenn `fAddRef` ist **"true"**, klicken Sie dann `AddRef` für den Aufruf von entsprechend den angegebenen Schnittstellenzeiger aufgerufen wird **Release** , der auftritt bei der `_variant_t` -Objekt zerstört wird. Es liegt bei Ihnen Aufrufen **Version** auf den bereitgestellten Schnittstellenzeiger auf. Wenn `fAddRef` ist **"false"**, übernimmt dieser Konstruktor den Besitz des angegebenen Schnittstellenzeigers, rufen Sie nicht **Version** auf den bereitgestellten Schnittstellenzeiger auf.  
  
-   **_variant_t( IDispatch\***  `pDispSrc` **, bool**  `fAddRef`  **= true )** Constructs a `_variant_t` object of type **VT_DISPATCH** from a COM interface pointer. Wenn `fAddRef` ist **"true"**, klicken Sie dann `AddRef` für den Aufruf von entsprechend den angegebenen Schnittstellenzeiger aufgerufen wird **Release** , der auftritt bei der `_variant_t` -Objekt zerstört wird. Es liegt bei Ihnen Aufrufen **Version** auf den bereitgestellten Schnittstellenzeiger auf. Wenn **fAddRef** ist "false", übernimmt dieser Konstruktor den Besitz von den bereitgestellten Schnittstellenzeiger auf, rufen Sie nicht **Version** auf den bereitgestellten Schnittstellenzeiger auf.  
  
-   **_variant_t( DECIMAL&**  `decSrc`  **)** Constructs a `_variant_t` object of type **VT_DECIMAL** from a **DECIMAL** value.  
  
-   **_variant_t( BYTE**  `bSrc`  **)** Constructs a `_variant_t` object of type `VT_UI1` from a **BYTE** value.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)