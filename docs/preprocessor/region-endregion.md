---
title: Region, Endregion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs: C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad2eb3d094447ae3ae35b0dbe9dc0fef2fe06710
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="region-endregion"></a>region, endregion
**#pragma Region** können Sie angeben, dass einen Codeblock, die Sie erweitern oder reduzieren bei Verwendung der [Gliederungsfunktion](/visualstudio/ide/outlining) des Code-Editors von Visual Studio.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>Parameter  
 `comment`(optional)  
 Ein Kommentar, der im Code-Editor angezeigt wird.  
  
 *Namen*(optional)  
 Der Name der Region.  Dieser Name wird im Code-Editor angezeigt.  
  
## <a name="remarks"></a>Hinweise  
 **#pragma Endregion** markiert das Ende einer **#pragma Region** Block.  
  
 Ein `#region` Block muss beendet werden, mit **#pragma Endregion**.  
  
## <a name="example"></a>Beispiel  
  
```  
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