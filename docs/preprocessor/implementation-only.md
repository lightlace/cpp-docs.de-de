---
title: Implementation_only | Microsoft-Dokumentation
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
ms.openlocfilehash: 2e7f0f40ad5d01b647f1f3273dc9a55d7cfa7564
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541584"
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
  
Die **Implementation_only** Attribut ist dazu vorgesehen, für die Verwendung in Verbindung mit der [No_implementation](../preprocessor/no-implementation.md) -Attribut als eine Möglichkeit, damit die Implementierungen nicht die vorkompilierte Headerdatei (PCH). Eine `#import`-Anweisung mit dem Attribut `no_implementation` wird in den Quellbereich eingefügt, der verwendet wird, um die PCH zu erstellen. Die resultierende PCH wird von mehreren Quelldateien verwendet. Ein `#import` -Anweisung mit der **Implementation_only** Attribut wird dann außerhalb des PCH-Bereichs verwendet. Sie müssen diese Anweisung nur einmal in einer der Quelldateien verwenden. Dadurch werden alle erforderlichen Wrappermemberfunktionen generiert, ohne dass eine zusätzliche Neukompilierung für jede Quelldatei erforderlich ist.  
  
> [!NOTE]
> Die **Implementation_only** Attribut in einem `#import` Anweisung muss es sich um die Verwendung in Verbindung mit einem anderen `#import` -Anweisung einer Typbibliothek, mit der `no_implementation` Attribut. Andernfalls werden Compilerfehler generiert. Dies ist, da die wrapperklassendefinitionen generiert die `#import` -Anweisung mit der `no_implementation` Attribut sind erforderlich, um die Implementierungen von generierten Kompilieren der **Implementation_only** Attribut.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)