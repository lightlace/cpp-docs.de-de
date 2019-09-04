---
title: region- und endregion-Pragmas
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: 4a01e04582ac81d678aa0702945c62ee974a4428
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222376"
---
# <a name="region-endregion-pragmas"></a>region- und endregion-Pragmas

`#pragma region`ermöglicht es Ihnen, einen Codeblock anzugeben, den Sie erweitern oder reduzieren können, wenn Sie die Gliederungs [Funktion](/visualstudio/ide/outlining) des Visual Studio Code-Editors verwenden.

## <a name="syntax"></a>Syntax

> **#pragma Region** *Name*\
> **#pragma endregion** *Kommentar*

### <a name="parameters"></a>Parameter

*geäußert*\
Optionale Ein Kommentar, der im Code-Editor angezeigt werden soll.

*Benennen*\
Optionale Der Name der Region. Dieser Name wird im Code-Editor angezeigt.

## <a name="remarks"></a>Hinweise

`#pragma endregion`markiert das Ende eines `#pragma region` -Blocks.

Ein `#region` -Block muss mit einer `#pragma endregion` -Direktive beendet werden.

## <a name="example"></a>Beispiel

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
