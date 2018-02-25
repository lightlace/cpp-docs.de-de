---
title: Auto_inline | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
dev_langs:
- C++
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 455d0b78b5807f92d0b675cd695b998c19abba48
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="autoinline"></a>auto_inline
Schließt alle Funktionen, die innerhalb des Bereichs definiert, in denen **deaktiviert** aus wird Betrachtung als Kandidaten für automatische Inlineerweiterung angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der **Auto_inline** Pragma, platzieren Sie es vor und unmittelbar nach (nicht in) einer Funktionsdefinition. Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)