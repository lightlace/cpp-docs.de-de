---
title: Auto_inline | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de012a31fe68c68d4e64df2d3fa10b44d9112735
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
ms.locfileid: "33954020"
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