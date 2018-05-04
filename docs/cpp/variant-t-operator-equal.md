---
title: _variant_t::Operator = | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0db0ea95fe3f5491780cd0297e8d3f56b6800e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="varianttoperator-"></a>_variant_t::operator =
**Microsoft-spezifisch**  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      _variant_t& operator=(  
   const VARIANT& varSrc   
);  
  
_variant_t& operator=(  
   const VARIANT* pVarSrc   
);  
  
_variant_t& operator=(  
   const _variant_t& var_t_Src   
);  
  
_variant_t& operator=(  
   short sSrc   
);  
  
_variant_t& operator=(  
   long lSrc   
);  
  
_variant_t& operator=(  
   float fltSrc   
);  
  
_variant_t& operator=(  
   double dblSrc   
);  
  
_variant_t& operator=(  
   const CY& cySrc   
);  
  
_variant_t& operator=(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t& operator=(  
   const wchar_t* wstrSrc   
);  
  
_variant_t& operator=(  
   const char* strSrc   
);  
  
_variant_t& operator=(  
   IDispatch* pDispSrc   
);  
  
_variant_t& operator=(  
   bool bSrc   
);  
  
_variant_t& operator=(  
   IUnknown* pSrc   
);  
  
_variant_t& operator=(  
   const DECIMAL& decSrc   
);  
  
_variant_t& operator=(  
   BYTE bSrc   
);  
  
_variant_t& operator=(  
   char cSrc  
);  
  
_variant_t& operator=(  
   unsigned short usSrc  
);  
  
_variant_t& operator=(  
   unsigned long ulSrc  
);  
  
_variant_t& operator=(  
   int iSrc  
);  
  
_variant_t& operator=(  
   unsigned int uiSrc  
);  
  
_variant_t& operator=(  
   __int64 i8Src  
);  
  
_variant_t& operator=(  
   unsigned __int64 ui8Src  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 Der Operator weist dem `_variant_t`-Objekt einen neuen Wert zu:  
  
-   **Operator = (***VarSrc***)** weist ein vorhandenes **VARIANT** zu einem `_variant_t` Objekt.      
  
-   **Operator = (***pvarSrc zeigt, stimmen***)** weist ein vorhandenes **VARIANT** zu einem `_variant_t` Objekt.      
  
-   **Operator = (***Var_t_Src***)** weist ein vorhandenes `_variant_t` -Objekt an eine `_variant_t` Objekt.      
  
-   **Operator = (***sSrc***)** weist eine **kurze** Integer-Wert, eine `_variant_t` Objekt.      
  
-   **Operator = (**`lSrc`**)** weist eine **lange** Integer-Wert, eine `_variant_t` Objekt.      
  
-   **Operator = (***FltSrc***)** weist eine **"float"** numerischen Wert ein `_variant_t` Objekt.      
  
-   **Operator = (***DblSrc***)** weist eine **doppelte** numerischen Wert ein `_variant_t` Objekt.      
  
-   **Operator = (***CySrc***)** weist eine **CY** -Objekt an eine `_variant_t` Objekt.      
  
-   **Operator = (***BstrSrc***)** weist eine `BSTR` -Objekt an eine `_variant_t` Objekt.      
  
-   **Operator = (***WstrSrc***)** weist eine Unicode-Zeichenfolge auf ein `_variant_t` Objekt.      
  
-   **Operator = (**`strSrc`**)** eine multibyte-Zeichenfolge weist ein `_variant_t` Objekt.      
  
-   **Operator = (** `bSrc` **)** weist eine `bool` -Wert an ein `_variant_t` Objekt.    
  
-   **Operator = (***pDispSrc***)** weist eine **VT_DISPATCH** -Objekt an eine `_variant_t` Objekt.      
  
-   **Operator = (***pIUnknownSrc***)** weist eine **VT_UNKNOWN** -Objekt an eine `_variant_t` Objekt.      
  
-   **Operator = (***DecSrc***)** weist eine **DECIMAL** -Wert an ein `_variant_t` Objekt.      
  
-   **Operator = (** `bSrc` **)** weist eine **BYTE** -Wert an ein `_variant_t` Objekt.    
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)