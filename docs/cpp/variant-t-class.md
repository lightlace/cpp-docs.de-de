---
title: _variant_t-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9315c2bb946cd80dd68153543ad6ae532ec9b7a0
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460867"
---
# <a name="variantt-class"></a>_variant_t-Klasse
**Microsoft-spezifisch**  
  
 Ein **_variant_t** -Objekt kapselt den `VARIANT` -Datentyp. Die Klasse verwaltet Ressourcen belegen und freigeben und führt Funktionsaufrufe von `VariantInit` und `VariantClear` je nach Bedarf.  
  
### <a name="construction"></a>Konstruktion  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Erstellt eine **_variant_t** Objekt.|  
  
### <a name="operations"></a>Vorgänge  
  
|||  
|-|-|  
|[Anfügen](../cpp/variant-t-attach.md)|Fügt eine `VARIANT` -Objekt in der **_variant_t** Objekt.|  
|[Clear](../cpp/variant-t-clear.md) (Löschen)|Löscht das gekapselte `VARIANT` Objekt.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Ändert den Typ des der **_variant_t** -Objekts in den angegebenen `VARTYPE`.|  
|[Trennen](../cpp/variant-t-detach.md)|Trennt das gekapselte `VARIANT` -Objekt aus diesem **_variant_t** Objekt.|  
|[SetString](../cpp/variant-t-setstring.md)|Weist eine Zeichenfolge zu diesem **_variant_t** Objekt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../cpp/variant-t-operator-equal.md)|Weist einen neuen Wert zu einem vorhandenen **_variant_t** Objekt.|  
|[Operator ==,! =](../cpp/variant-t-relational-operators.md)|Vergleichen Sie zwei **_variant_t** -Objekte auf Gleichheit bzw. Ungleichheit.|  
|[Extraktoren](../cpp/variant-t-extractors.md)|Extrahieren von Daten aus dem gekapselten `VARIANT` Objekt.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<comutil.h>  
  
 **LIB:** comsuppw.lib oder comsuppwd.lib (finden Sie unter [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)