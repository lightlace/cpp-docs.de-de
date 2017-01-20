---
title: "_variant_t::operator ="
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
  - "_variant_t.operator="
  - "_variant_t::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "=-Operator, Mit spezifischen Visual C++-Objekten"
  - "Operator =, variant"
  - "Operator=, variant"
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::operator =
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
## Syntax  
  
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
  
## Hinweise  
 Der Operator weist dem `_variant_t`\-Objekt einen neuen Wert zu:  
  
-   **operator\=\(**  *varSrc*  **\)** Weist ein vorhandenes **VARIANT**\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *pVarSrc*  **\)** Weist ein vorhandenes **VARIANT**\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *var\_t\_Src*  **\)** Weist ein vorhandenes `_variant_t`\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *sSrc*  **\)** Weist einen **short**\-Ganzzahlwert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  `lSrc`  **\)** Weist einen **long**\-Ganzzahlwert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *fltSrc*  **\)** Weist einen numerischen **float**\-Wert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *dblSrc*  **\)** Weist einen numerischen **double**\-Wert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *cySrc*  **\)** Weist ein **CY**\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *bstrSrc*  **\)** Weist ein `BSTR`\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *wstrSrc*  **\)** Weist eine Unicodezeichenfolge einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  `strSrc`  **\)** Weist eine Multibytezeichenfolge einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  `bSrc` **\)** Weist einen `bool`\-Wert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *pDispSrc*  **\)** Weist ein **VT\_DISPATCH**\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *pIUnknownSrc*  **\)** Weist ein **VT\_UNKNOWN**\-Objekt einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  *decSrc*  **\)** Weist einen **DECIMAL**\-Wert einem `_variant_t`\-Objekt zu.  
  
-   **operator\=\(**  `bSrc` **\)** Weist einen **BYTE**\-Wert einem `_variant_t`\-Objekt zu.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)