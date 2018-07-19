---
title: Include() | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- include()
dev_langs:
- C++
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 756aea4400d98b2bf061a54955b3df4b4eddd993
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849274"
---
# <a name="include"></a>include()
**C++-spezifisch**  
  
 Deaktiviert den automatische Ausschluss.  
  
## <a name="syntax"></a>Syntax  
  
```  
include("Name1"[,"Name2", ...])  
```  
  
#### <a name="parameters"></a>Parameter  
 `Name1`  
 Das erste Element, dessen Aufnahme erzwungen wird.  
  
 `Name2`  
 Das zweite Element, dessen Aufnahme erzwungen wird (falls erforderlich).  
  
## <a name="remarks"></a>Hinweise  
 Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache Definitionsfehler dadurch zu vermeiden, dass solche Elemente automatisch ausgeschlossen werden. Wenn Elemente durch ausgeschlossen wurden, [Compilerwarnung (Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), und es sollten keine wurden, dieses Attribut kann verwendet werden, an die automatischen Ausschluss deaktivieren. Dieses Attribut kann eine beliebige Anzahl von Argumenten akzeptieren, die jeweils der Name des einzuschließenden Typbibliothekelements sind.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)