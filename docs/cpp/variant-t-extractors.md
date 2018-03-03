---
title: _variant_t-extraktoren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs:
- C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8876cd486662ec1c20aea7148563fd28e8790a47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="variantt-extractors"></a>_variant_t-Extraktoren
**Microsoft-spezifisch**  
  
 Extrahieren von Daten aus dem gekapselten **VARIANT** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="remarks"></a>Hinweise  
 Extrahiert Rohdaten aus einem gekapselten **VARIANT**. Wenn die **VARIANT** ist bereits nicht der richtige Typ **VariantChangeType** wird verwendet, um eine Konvertierung zu versuchen und bei einem Fehler wird ein Fehler generiert:  
  
-   **Operator short ()** extrahiert eine **kurze** Integer-Wert.  
  
-   **Operator long ()** extrahiert eine **lange** Integer-Wert.  
  
-   **Operator float ()** extrahiert eine **"float"** numerischen Wert.  
  
-   **Operator double ()** extrahiert eine **doppelte** Integer-Wert.  
  
-   **Operator CY ()** extrahiert eine **CY** Objekt.  
  
-   **Operator Bool ()** extrahiert eine `bool` Wert.  
  
-   **Operator DECIMAL ()** extrahiert eine **DECIMAL** Wert.  
  
-   **Operator BYTE ()** extrahiert eine **BYTE** Wert.  
  
-   **Operator _bstr_t ()** extrahiert eine Zeichenfolge, die in einem gekapselt ist ein `_bstr_t` Objekt.  
  
-   **Operator IDispatch\*()** extrahiert einen Disp-Schnittstellenzeiger aus einem gekapselten **VARIANT**. `AddRef`wird auf dem resultierenden Zeiger aufgerufen, also entscheiden, ob Sie rufen **Version** um ihn freizugeben.  
  
-   **Operator IUnknown\*()** extrahiert einen COM-Schnittstellenzeiger aus einem gekapselten **VARIANT**. `AddRef`wird auf dem resultierenden Zeiger aufgerufen, also entscheiden, ob Sie rufen **Version** um ihn freizugeben.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)
