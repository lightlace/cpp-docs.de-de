---
title: Compilerwarnung C4335 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adb8a7b484ce0946f385c3b2a8669ba1b5ccf0d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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