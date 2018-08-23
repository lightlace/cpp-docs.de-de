---
title: No_auto_exclude | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_auto_exclude
dev_langs:
- C++
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5cae3a52c3434317ee26292de13d3e0471d78998
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2018
ms.locfileid: "42540419"
---
# <a name="noautoexclude"></a>no_auto_exclude
**C++-spezifisch**  
  
Deaktiviert den automatische Ausschluss.  
  
## <a name="syntax"></a>Syntax  
  
```  
no_auto_exclude  
```  
  
## <a name="remarks"></a>Hinweise  
 
Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden. Wenn dies abgeschlossen ist, [Compilerwarnung (Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) für die einzelnen Elemente ausgeschlossen werden ausgegeben. Sie können diesen automatischen Ausschluss deaktivieren, indem Sie dieses Attribut verwenden.  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 
[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)