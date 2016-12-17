---
title: "_variant_t-Klasse"
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
  - "Variant"
  - "_variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t-Klasse"
  - "_variant_t-Klasse, Memberfunktionen"
  - "_variant_t-Klasse, Operatoren"
  - "VARIANT-Objekt"
  - "VARIANT-Objekt, COM-Kapselung"
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ein `_variant_t`\-Objekt kapselt den `VARIANT`\-Datentyp ein.  Die Klasse verwaltet die Zuordnung und Neuzuordnung von Ressourcen und führt Funktionsaufrufe von **VariantInit** und **VariantClear** durch, sofern erforderlich.  
  
### Konstruktion  
  
|||  
|-|-|  
|[\_variant\_t](../cpp/variant-t-variant-t.md)|Erstellt ein `_variant_t`\-Objekt.|  
  
### Vorgänge  
  
|||  
|-|-|  
|[Anfügen](../cpp/variant-t-attach.md)|Fügt ein **VARIANT**\-Objekt an das `_variant_t`\-Objekt an.|  
|[Clear](../cpp/variant-t-clear.md)|Löscht das gekapselte **VARIANT**\-Objekt.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Ändert den Typ des `_variant_t`\-Objekts in den angegebenen **VARTYPE**.|  
|[Trennen](../cpp/variant-t-detach.md)|Trennt das gekapselte **VARIANT**\-Objekt von diesem `_variant_t`\-Objekt.|  
|[SetString](../cpp/variant-t-setstring.md)|Weist diesem `_variant_t`\-Objekt eine Zeichenfolge zu.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \=](../cpp/variant-t-operator-equal.md)|Weist einem vorhandenen `_variant_t`\-Objekt einen neuen Wert zu.|  
|[operator \=\=, \!\=](../cpp/variant-t-relational-operators.md)|Überprüft zwei `_variant_t`\-Objekte auf Gleichheit bzw. Ungleichheit.|  
|[Extractors](../cpp/variant-t-extractors.md)|Extrahiert Daten aus dem gekapselten **VARIANT**\-Objekt.|  
  
## Ende Microsoft\-spezifisch  
  
## Anforderungen  
 **Header:** comutil.h  
  
 **Lib:** comsuppw.lib oder comsuppwd.lib \(Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).\)  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)