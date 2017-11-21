---
title: _variant_t-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _variant_t
dev_langs: C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1afc35836f170a03ec7b8f4d8e20a1ff02995c23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="variantt-class"></a>_variant_t-Klasse
**Microsoft-spezifisch**  
  
 Ein `_variant_t`-Objekt kapselt den `VARIANT`-Datentyp ein. Die Klasse verwaltet die Zuordnung und Aufhebung der Zuordnung und führt Funktionsaufrufe von **VariantInit** und **VariantClear** je nach Bedarf.  
  
### <a name="construction"></a>Konstruktion  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Erstellt ein `_variant_t`-Objekt.|  
  
### <a name="operations"></a>Vorgänge  
  
|||  
|-|-|  
|[Anfügen](../cpp/variant-t-attach.md)|Fügt eine **VARIANT** -Objekt in der `_variant_t` Objekt.|  
|[Clear](../cpp/variant-t-clear.md) (Löschen)|Löscht das gekapselte **VARIANT** Objekt.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Ändert den Typ des der `_variant_t` Objekt für das angezeigte **VARTYPE**.|  
|[Trennen](../cpp/variant-t-detach.md)|Trennt das gekapselte **VARIANT** -Objekt von diesem `_variant_t` Objekt.|  
|[SetString](../cpp/variant-t-setstring.md)|Weist diesem `_variant_t`-Objekt eine Zeichenfolge zu.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../cpp/variant-t-operator-equal.md)|Weist einem vorhandenen `_variant_t`-Objekt einen neuen Wert zu.|  
|[Operator ==,! =](../cpp/variant-t-relational-operators.md)|Überprüft zwei `_variant_t`-Objekte auf Gleichheit bzw. Ungleichheit.|  
|[Extraktoren](../cpp/variant-t-extractors.md)|Extrahieren von Daten aus dem gekapselten **VARIANT** Objekt.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** comutil.h  
  
 **LIB:** "comsuppw.lib" oder "comsuppwd.lib" (siehe [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) für Weitere Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)