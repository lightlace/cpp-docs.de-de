---
title: Auto_rename | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- auto_rename
dev_langs:
- C++
helpviewer_keywords:
- auto_rename attribute
ms.assetid: 1075f3ab-f6fc-4e04-8e22-ebe02695a567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7561e9d9b49f9af885299a6b94d3edbcf8f2a74
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912809"
---
# <a name="autorename"></a>auto_rename
**C++-spezifisch**  
  
 Benennt für C++ reservierte Wörter um, indem dem Variablennamen zwei Unterstriche (__) angefügt werden, um potenzielle Namenskonflikte zu vermeiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
auto_rename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Attribut wird verwendet, wenn Sie eine Typbibliothek importierten, die eine oder mehrere für C++ reservierte Wörter (Schlüsselwörter oder Makros) als Variablennamen verwendet.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)