---
title: implementation_only
ms.date: 11/04/2016
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: c1435ca74ac2b5a73c308592b1affe6fca097d1b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026653"
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

Die **Implementation_only** Attribut ist dazu vorgesehen, für die Verwendung in Verbindung mit der [No_implementation](../preprocessor/no-implementation.md) -Attribut als eine Möglichkeit, damit die Implementierungen nicht die vorkompilierte Headerdatei (PCH). Eine `#import`-Anweisung mit dem Attribut `no_implementation` wird in den Quellbereich eingefügt, der verwendet wird, um die PCH-Datei zu erstellen. Die resultierende PCH wird von mehreren Quelldateien verwendet. Ein `#import` -Anweisung mit der **Implementation_only** Attribut wird dann außerhalb des PCH-Bereichs verwendet. Sie müssen diese Anweisung nur einmal in einer der Quelldateien verwenden. Dadurch werden alle erforderlichen Wrappermemberfunktionen generiert, ohne dass eine zusätzliche Neukompilierung für jede Quelldatei erforderlich ist.

> [!NOTE]
> Die **Implementation_only** Attribut in einem `#import` Anweisung muss es sich um die Verwendung in Verbindung mit einem anderen `#import` -Anweisung einer Typbibliothek, mit der `no_implementation` Attribut. Andernfalls werden Compilerfehler generiert. Dies ist, da die wrapperklassendefinitionen generiert die `#import` -Anweisung mit der `no_implementation` Attribut sind erforderlich, um die Implementierungen von generierten Kompilieren der **Implementation_only** Attribut.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)