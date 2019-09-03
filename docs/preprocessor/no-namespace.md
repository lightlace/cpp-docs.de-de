---
title: no_namespace-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: ba52aed69cdbb46c135e6de5078d718e93f99c87
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220740"
---
# <a name="no_namespace-import-attribute"></a>no_namespace-Attribut importieren

**C++Zugeschnitten**

Gibt an, dass der Compiler keinen Namespace Namen generiert.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **no_namespace**

## <a name="remarks"></a>Hinweise

Der Inhalt der Typbibliothek in der `#import`-Headerdatei wird normalerweise in einem Namespace definiert. Der Namespace Name wird in der `library` -Anweisung der ursprünglichen IDL-Datei angegeben. Wenn das **no_namespace** -Attribut angegeben ist, wird dieser Namespace nicht vom Compiler generiert.

Wenn Sie einen anderen Namespace Namen verwenden möchten, verwenden Sie stattdessen das [rename_namespace](../preprocessor/rename-namespace.md) -Attribut.

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
