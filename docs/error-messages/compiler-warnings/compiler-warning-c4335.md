---
title: Compilerwarnung C4335 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ab7406a9c161d47e431cb0af8183d99eac7bfe86
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4335"></a>Compilerwarnung C4335
Mac-Dateiformat erkannt: Konvertieren Sie die Quelldatei in DOS oder UNIX-Format  
  
 Die Beendigung-Zeile-Zeichen von der ersten Zeile einer Quelldatei ist Macintosh-Systeme ("\r") im Gegensatz zu UNIX ("\n") oder DOS ("\r\n").  
  
 Diese Warnung wird immer als Fehler ausgegeben.  Finden Sie unter [Warnung](../../preprocessor/warning.md) Pragma Informationen dazu, wie Sie diese Warnung zu deaktivieren.  Darüber hinaus wird diese Warnung nur einmal pro Kompiliereinheit ausgegeben. Aus diesem Grund treten mehrere `#include` Direktiven, die Dateien im Macintosh-Format angeben, wird C4335 wird nur einmal ausgegeben.  
  
 Eine Möglichkeit zum Generieren von Dateien im Macintosh-Format ist mit der **Erweiterte Speicheroptionen** (auf der **Datei** Menü) in Visual Studio.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4335 generiert.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```
