---
title: Implementation_only | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: implementation_only
dev_langs: C++
helpviewer_keywords: implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a033cd4b1618c2da106bb641f55c9ae967cd53a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementationonly"></a>implementation_only
**C++-spezifisch**  
  
 Unterdrückt die Generierung der TLH-Headerdatei (die primäre Headerdatei).  
  
## <a name="syntax"></a>Syntax  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Datei enthält alle Deklarationen, die verwendet werden, um den Inhalt der Typbibliothek verfügbar zu machen. Die TLI-Headerdatei wird mit den implementierten Wrappermemberfunktionen generiert und in die Kompilierung aufgenommen.  
  
 Wenn dieses Attribut festgelegt ist, befindet sich der Inhalt des TLI-Headers im selben Namespace wie der, der normalerweise im TLH-Header verwendet wird. Außerdem werden die Memberfunktionen nicht als Inline deklariert.  
  
 Die `implementation_only` Attribut dient zur Verwendung in Verbindung mit der [No_implementation](../preprocessor/no-implementation.md) Attribut als eine Möglichkeit der Implementierungen aus der vorkompilierten Headerdatei (PCH). Eine `#import`-Anweisung mit dem Attribut `no_implementation` wird in den Quellbereich eingefügt, der verwendet wird, um die PCH zu erstellen. Die resultierende PCH wird von mehreren Quelldateien verwendet. Eine `#import`-Anweisung mit dem Attribut `implementation_only` wird dann außerhalb des PCH-Bereichs verwendet. Sie müssen diese Anweisung nur einmal in einer der Quelldateien verwenden. Dadurch werden alle erforderlichen Wrappermemberfunktionen generiert, ohne dass eine zusätzliche Neukompilierung für jede Quelldatei erforderlich ist.  
  
> [!NOTE]
>  Das Attribut `implementation_only` in einer `#import`-Anweisung muss zusammen mit einer anderen `#import`-Anweisung (derselben Typbibliothek) mit dem Attribut `no_implementation` verwendet werden. Andernfalls werden Compilerfehler generiert. Dies liegt daran, dass die Wrapperklassendefinitionen, die durch die `#import`-Anweisung mit dem Attribut `no_implementation` generiert werden, erforderlich sind, die Implementierungen zu kompilieren, die vom Attribut `implementation_only` generiert werden.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)