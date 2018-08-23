---
title: Region, Endregion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e6ec22be873dcec06f224913eb905a2779e4efd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540793"
---
# <a name="region-endregion"></a>region, endregion
`#pragma region` können Sie angeben, dass einen Codeblock, der Sie können erweitert oder reduziert werden, wenn Sie verwenden die [Gliederungsfunktion](/visualstudio/ide/outlining) von Visual Studio Code-Editor.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
### <a name="parameters"></a>Parameter  
*Kommentar* (optional)  
Ein Kommentar, der im Code-Editor angezeigt wird.  
  
*name* (optional)  
Der Name der Region.  Dieser Name wird im Code-Editor angezeigt.  
  
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