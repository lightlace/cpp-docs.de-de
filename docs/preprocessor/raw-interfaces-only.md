---
title: Raw_interfaces_only | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_interfaces_only
dev_langs: C++
helpviewer_keywords: raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d7790601a3eec16cae67542ac2d8d622b71df2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++-spezifisch**  
  
 Unterdrückt die Generierung des Fehlerbehandlungs-Wrapperfunktionen und [Eigenschaft](../cpp/property-cpp.md) Deklarationen, die diese Wrapperfunktionen verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
raw_interfaces_only  
```  
  
## <a name="remarks"></a>Hinweise  
 Das `raw_interfaces_only`-Attribut bewirkt auch die Entfernung des Standardpräfixes, das beim Benennen der Funktionen, die keine Eigenschaften sind, verwendet wird. In der Regel wird das Präfix ist **Raw_**. Wenn dieses Attribut festgelegt wird, stammen die Funktionsnamen direkt aus der Typbibliothek.  
  
 Dieses Attribut ermöglicht, dass Sie nur die Inhalte auf niedriger Ebene aus der Typbibliothek verfügbar machen.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)