---
title: Raw_native_types | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4908f1f06ef0479121d3ec5ac8fa56a797ed05ca
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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