---
title: region, endregion
ms.date: 10/18/2018
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
ms.openlocfilehash: c73a90aa2be83d643b74dde4645081e89da3ff73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179749"
---
# <a name="region-endregion"></a>region, endregion

`#pragma region` können Sie angeben, dass einen Codeblock, der Sie können erweitert oder reduziert werden, wenn Sie verwenden die [Gliederungsfunktion](/visualstudio/ide/outlining) von Visual Studio Code-Editor.

## <a name="syntax"></a>Syntax

```
#pragma region name
#pragma endregion comment
```

### <a name="parameters"></a>Parameter

*comment*<br/>
(Optional) Ein Kommentar, der im Code-Editor angezeigt wird.

*name*<br/>
(Optional) Der Name des Bereichs.  Dieser Name wird im Code-Editor angezeigt.

## <a name="remarks"></a>Hinweise

`#pragma endregion` markiert das Ende einer `#pragma region` Block.

Ein `#region` Block muss mit abgeschlossen werden `#pragma endregion`.

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