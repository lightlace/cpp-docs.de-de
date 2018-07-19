---
title: Implementation_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- implementation_only
dev_langs:
- C++
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a3a2cbf0b39dc1c5f5462ae105e2206d70a38f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912822"
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