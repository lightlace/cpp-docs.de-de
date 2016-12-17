---
title: "_variant_t::_variant_t"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::_variant_t"
  - "_variant_t._variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t-Klasse, Konstruktor"
  - "_variant_t-Methode"
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::_variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erstellt ein `_variant_t`\-Objekt.  
  
## Syntax  
  
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
  
#### Parameter  
 *varSrc*  
 Ein **VARIANT**\-Objekt, das in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *pVarSrc*  
 Zeiger auf ein **VARIANT**\-Objekt, das in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *var\_t\_Src*  
 Ein `_variant_t`\-Objekt, das in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `fCopy`  
 Wenn "false", wird das bereitgestellte **VARIANT**\-Objekt an das neue `_variant_t`\-Objekt angefügt, ohne dass mit **VariantCopy** eine neue Kopie erstellt wird.  
  
 *ISrc, sSrc*  
 Ein ganzer Wert, der in das neue `_variant_t` \-Objekt kopiert werden soll.  
  
 `vtSrc`  
 Der **VARTYPE** für das neue `_variant_t`\-Objekt.  
  
 *fltSrc, dblSrc*  
 Ein in das neue `_variant_t`\-Objekt zu kopierender numerischer Wert.  
  
 `cySrc`  
 Ein **CV**\-Objekt, das in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `bstrSrc`  
 Ein `_bstr_t`\-Objekt, das in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *strSrc, wstrSrc*  
 Eine Zeichenfolge, die in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `bSrc`  
 Ein `bool`\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `pIUknownSrc`  
 COM\-Schnittstellenzeiger auf ein **VT\_UNKNOWN**\-Objekt, das in ein neues `_variant_t`\-Objekt gekapselt wird.  
  
 `pDispSrc`  
 COM\-Schnittstellenzeiger auf ein **VT\_DISPATCH**\-Objekt, das in ein neues `_variant_t`\-Objekt gekapselt wird.  
  
 `decSrc`  
 Ein **DECIMAL**\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `bSrc`  
 Ein **BYTE**\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `cSrc`  
 Ein `char`\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *usSrc*  
 Ein in das neue `_variant_t`\-Objekt zu kopierender **unsigned short**\-Wert.  
  
 *ulSrc*  
 Ein `unsigned long`\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 `iSrc`  
 Ein `int`\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *uiSrc*  
 Ein `unsigned int`\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *i8Src*  
 Ein \_\_**int64**\-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
 *ui8Src*  
 Ein **unsigned \_\_int64** \-Wert, der in das neue `_variant_t`\-Objekt kopiert werden soll.  
  
## Hinweise  
  
-   **\_variant\_t\( \)** Erstellt ein leeres `_variant_t`\-Objekt, `VT_EMPTY`.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc*  **\)** Erstellt ein `_variant_t`\-Objekt aus einer Kopie des **VARIANT**\-Objekts.  Der Varianttyp wird beibehalten.  
  
-   **\_variant\_t\( VARIANT\***  *pVarSrc*  **\)** Erstellt ein `_variant_t`\-Objekt aus einer Kopie des **VARIANT**\-Objekts.  Der Varianttyp wird beibehalten.  
  
-   **\_variant\_t\( \_variant\_t&**  *var\_t\_Src*  **\)** Erstellt ein `_variant_t`\-Objekt aus einem anderen `_variant_t`\-Objekt.  Der Varianttyp wird beibehalten.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc* **, bool**  `fCopy`  **\)** Erstellt ein `_variant_t`\-Objekt aus einem vorhandenen **VARIANT**\-Objekt.  Wenn `fCopy` den Wert **false** hat, wird das **VARIANT**\-Objekt an das neue Objekt angefügt, ohne dass eine Kopie erstellt wird.  
  
-   **\_variant\_t\( short**  *sSrc* **, VARTYPE**  `vtSrc`  **\= VT\_I2 \)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_I2` oder `VT_BOOL` aus einem ganzzahligen **short**\-Wert.  Jeder andere **VARTYPE** führt zu einem `E_INVALIDARG`\-Fehler.  
  
-   **\_variant\_t\( long**  `lSrc` **, VARTYPE**  `vtSrc`  **\= VT\_I4 \)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_I4`, `VT_BOOL` oder `VT_ERROR` aus einem ganzzahligen **long**\-Wert.  Jeder andere **VARTYPE** führt zu einem `E_INVALIDARG`\-Fehler.  
  
-   **\_variant\_t\( float**  `fltSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_R4` aus einem numerischen **float**\-Wert.  
  
-   **\_variant\_t\( double**  `dblSrc` **, VARTYPE**  `vtSrc`  **\= VT\_R8 \)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_R8` oder `VT_DATE` aus einem numerischen **double**\-Wert.  Jeder andere **VARTYPE** führt zu einem `E_INVALIDARG`\-Fehler.  
  
-   **\_variant\_t\( CY&**  `cySrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_CY` aus einem **CY**\-Objekt.  
  
-   **\_variant\_t\( \_bstr\_t&**  `bstrSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_BSTR` aus einem `_bstr_t`\-Objekt.  Ein neues `BSTR` wird zugeordnet.  
  
-   **\_variant\_t\( wchar\_t \*** *wstrSrc*  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_BSTR` aus einer Unicode\-Zeichenfolge.  Ein neues `BSTR` wird zugeordnet.  
  
-   **\_variant\_t\( char\***  `strSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_BSTR` aus einer Zeichenfolge.  Ein neues `BSTR` wird zugeordnet.  
  
-   **\_variant\_t\( bool**  `bSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_BOOL` aus einem `bool`\-Wert.  
  
-   **\_variant\_t\( IUnknown\***  `pIUknownSrc` **, bool**  `fAddRef`  **\= true \)** Erstellt ein `_variant_t`\-Objekt vom Typ **VT\_UNKNOWN** aus einem COM\-Schnittstellenzeiger.  Wenn `fAddRef` den Wert **true** hat, wird `AddRef` für den angegebenen Schnittstellenzeiger aufgerufen, um den Aufruf an **Release** anzupassen, der auftritt, wenn das `_variant_t`\-Objekt beschädigt wird.  Sie können entscheiden, ob Sie **Release** für den bereitgestellten Schnittstellenzeiger aufrufen.  Wenn `fAddRef` den Wert **false** hat, übernimmt dieser Konstruktor den Besitz des angegebenen Schnittstellenzeigers. Rufen Sie **Release** nicht für den bereitgestellten Schnittstellenzeiger auf.  
  
-   **\_variant\_t\( IDispatch\***  `pDispSrc` **, bool**  `fAddRef`  **\= true \)** Erstellt ein `_variant_t`\-Objekt vom Typ **VT\_DISPATCH** aus einem COM\-Schnittstellenzeiger.  Wenn `fAddRef` den Wert **true** hat, wird `AddRef` für den angegebenen Schnittstellenzeiger aufgerufen, um den Aufruf an **Release** anzupassen, der auftritt, wenn das `_variant_t`\-Objekt beschädigt wird.  Sie können entscheiden, ob Sie **Release** für den bereitgestellten Schnittstellenzeiger aufrufen.  Wenn **fAddRef** den Wert "false" hat, übernimmt dieser Konstruktor den Besitz des angegebenen Schnittstellenzeigers. Rufen Sie **Release** nicht für den bereitgestellten Schnittstellenzeiger auf.  
  
-   **\_variant\_t\( DECIMAL&**  `decSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ **VT\_DECIMAL** aus einem **DECIMAL**\-Wert.  
  
-   **\_variant\_t\( BYTE**  `bSrc`  **\)** Erstellt ein `_variant_t`\-Objekt vom Typ `VT_UI1` aus einem **BYTE**\-Wert.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)