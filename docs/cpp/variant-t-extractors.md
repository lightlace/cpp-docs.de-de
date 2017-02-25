---
title: "_variant_t-Extraktoren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operatordouble"
  - "operatorlong"
  - "_variant_t::operator_bstr_t"
  - "operatordouble"
  - "_variant_t.operatorCY"
  - "operatorCY"
  - "_variant_t::operatorCY"
  - "_variant_t::operatordouble"
  - "operatorfloat"
  - "operatorBYTE"
  - "_variant_t.operatorDECIMAL"
  - "_variant_t::operatorlong"
  - "operatorIDispatch"
  - "_variant_t.operatorBYTE"
  - "operatorDECIMAL"
  - "_variant_t.operator_bstr_t"
  - "_variant_t::operatorDECIMAL"
  - "_variant_t.operatorIUnknown"
  - "_variant_t.operatorlong"
  - "_variant_t::operatorIDispatch"
  - "_variant_t::operatorIUnknown"
  - "operatorIUnknown"
  - "_variant_t.operatorbool"
  - "_variant_t::operatorBYTE"
  - "_variant_t.operatorfloat"
  - "operator_bstr_t"
  - "_variant_t::operatorbool"
  - "operatorshort"
  - "_variant_t::operatorshort"
  - "_variant_t::operatorfloat"
  - "_variant_t.operatorIDispatch"
  - "_variant_t.operatorshort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Extraktoren, _variant_t-Klasse"
  - "Operator _bstr_t"
  - "operator bool"
  - "Operator BYTE"
  - "Operator CY"
  - "Operator DECIMAL"
  - "Operator double"
  - "Operator float"
  - "Operator IDispatch"
  - "Operator IUnknown"
  - "Operator long"
  - "Operator SHORT"
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t-Extraktoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Extrahiert Daten aus dem gekapselten **VARIANT**\-Objekt.  
  
## Syntax  
  
```  
  
      operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## Hinweise  
 Extrahiert Rohdaten aus einem gekapselten **VARIANT**\-Typ.  Wenn **VARIANT** noch nicht der richtige Typ ist, wird **VariantChangeType** verwendet, um eine Konvertierung zu versuchen, und beim Fehlschlagen wird ein Fehler generiert:  
  
-   **operator short\( \)** Extrahiert einen **short**\-Ganzzahlwert.  
  
-   **operator long\( \)** Extrahiert einen **long**\-Ganzzahlwert.  
  
-   **operator float\( \)** Extrahiert einen numerischen **float**\-Wert.  
  
-   **operator double\( \)** Extrahiert einen **double**\-Ganzzahlwert.  
  
-   **operator CY\( \)** Extrahiert ein **CY**\-Objekt.  
  
-   **operator bool\( \)** Extrahiert einen `bool`\-Wert.  
  
-   **operator DECIMAL\( \)** Extrahiert einen **DECIMAL**\-Wert.  
  
-   **operator BYTE\( \)** Extrahiert einen **BYTE**\-Wert.  
  
-   **operator \_bstr\_t\( \)** Extrahiert eine Zeichenfolge, die in einem `_bstr_t`\-Objekt gekapselt wird.  
  
-   **operator IDispatch\*\( \)** Extrahiert einen Disp\-Schnittstellenzeiger aus einer gekapselten **VARIANT**.  `AddRef` wird auf dem resultierenden Zeiger aufgerufen, es liegt daher an Ihnen, **Release** aufzurufen, um ihn freizugeben.  
  
-   **operator IUnknown\*\( \)** Extrahiert einen COM\-Schnittstellenzeiger aus einem gekapselten **VARIANT**.  `AddRef` wird auf dem resultierenden Zeiger aufgerufen, es liegt daher an Ihnen, **Release** aufzurufen, um ihn freizugeben.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_variant\_t\-Klasse](../cpp/variant-t-class.md)