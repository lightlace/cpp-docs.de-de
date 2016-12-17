---
title: "_bstr_t::operator +=, +"
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
  - "_bstr_t::operator+"
  - "_bstr_t::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+-Operator, _bstr_t-Objekte"
  - "+=-Operator, Anfügen von Zeichenfolgen"
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator +=, +
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Fügt Zeichen am Ende des `_bstr_t`\-Objekts hinzu oder verkettet zwei Zeichenfolgen.  
  
## Syntax  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### Parameter  
 *s1*  
 Ein `_bstr_t`\-Objekt.  
  
 *s2*  
 Eine Mehrbytezeichenfolge.  
  
 `s3`  
 Eine Unicode\-Zeichenfolge.  
  
## Hinweise  
 Diese Operatoren führen eine Zeichenfolgenverkettung aus:  
  
-   **operator\+\=\(**  *s1*  **\)** Fügt die Zeichen im gekapselten `BSTR` von *s1* dem Ende des gekapselten `BSTR` dieses Objekts an.  
  
-   **operator\+\(**  *s1*  **\)** Gibt das neue `_bstr_t` zurück, das durch die Verkettung des `BSTR` dieses Objekts mit dem von *s1* gebildet wird.  
  
-   **operator\+\(**  *s2*  **&#124;**  *s1*  **\)** Gibt ein neues `_bstr_t` zurück, das durch die Verkettung einer Mehrbytezeichenfolge *s2* \(in Unicode konvertiert\) mit `BSTR` \(in *s1* gekapselt\) gebildet wird.  
  
-   **operator\+\(**  `s3` **,**  *s1*  **\)** Gibt ein neues `_bstr_t` zurück, das durch die Verkettung einer Unicode\-Zeichenfolge `s3` mit dem `BSTR` gebildet wird, das in *s1* gekapselt ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)