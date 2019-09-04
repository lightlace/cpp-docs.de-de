---
title: implementation_only-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 08144b3c815350acfe6a856b36d2d88085d1c04d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218977"
---
# <a name="implementation_only-import-attribute"></a>implementation_only-Attribut importieren

**C++Zugeschnitten**

Unterdrückt die Generierung `.tlh` der primären Typbibliotheks-Header Datei.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **implementation_only**

## <a name="remarks"></a>Hinweise

Diese Datei enthält alle Deklarationen, die verwendet werden, um den Inhalt der Typbibliothek verfügbar zu machen. Die `.tli` Header Datei wird mit den Implementierungen der Wrapper Element Funktionen generiert und in die Kompilierung eingeschlossen.

Wenn dieses Attribut angegeben wird, befindet sich der Inhalt `.tli` des Headers im gleichen Namespace wie der, der normalerweise `.tlh` im Header verwendet wird. Außerdem werden die Memberfunktionen nicht als Inline deklariert.

Das **implementation_only** -Attribut ist für die Verwendung in Verbindung mit dem [no_implementation](../preprocessor/no-implementation.md) -Attribut vorgesehen, um die Implementierungen aus der vorkompilierten Header Datei (PCH) zu halten. Eine `#import`-Anweisung mit dem Attribut `no_implementation` wird in den Quellbereich eingefügt, der verwendet wird, um die PCH-Datei zu erstellen. Die resultierende PCH wird von mehreren Quelldateien verwendet. Eine `#import` -Anweisung mit dem **implementation_only** -Attribut wird dann außerhalb der PCH-Region verwendet. Diese Anweisung muss nur einmal in einer der Quelldateien verwendet werden. Sie generiert alle erforderlichen Wrapper Element Funktionen ohne zusätzliche Neukompilierung für jede Quelldatei.

> [!NOTE]
> Das **implementation_only** -Attribut in `#import` einer Anweisung muss zusammen mit einer anderen `#import` -Anweisung der gleichen Typbibliothek mit dem `no_implementation` -Attribut verwendet werden. Andernfalls werden Compilerfehler generiert. Dies liegt daran, dass die von der `#import` -Anweisung mit dem `no_implementation` -Attribut generierten Wrapper Klassendefinitionen erforderlich sind, um die vom **implementation_only** -Attribut generierten Implementierungen zu kompilieren.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
