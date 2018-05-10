---
title: Raw_native_types | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5baa3204b14da53f6a6a3232874e0ac7de0fd91b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="rawnativetypes"></a>raw_native_types
**C++-spezifisch**  
  
 Deaktiviert die Verwendung COM-Unterstützungsklassen in den Wrapperfunktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig verwenden die Fehlerbehandlungsmethoden auf hoher Ebene die COM-Unterstützungsklassen [_bstr_t](../cpp/bstr-t-class.md) und [_variant_t](../cpp/variant-t-class.md) anstelle von der `BSTR` und **VARIANT** Datentypen und unformatierten COM-Schnittstellenzeiger. Diese Klassen kapseln die Details der Zuordnung und Freigabe des Arbeitsspeichers für diese Datentypen und vereinfachen die Typumwandlungs- und Konvertierungsoperationen erheblich.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)