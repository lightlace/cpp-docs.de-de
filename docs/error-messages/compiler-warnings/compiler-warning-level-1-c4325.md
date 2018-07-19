---
title: Compilerwarnung (Stufe 1) C4325 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936433987f823ae7d5d22cfd075f188dd5d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277643"
---
# <a name="compiler-warning-level-1-c4325"></a>Compilerwarnung (Stufe 1) C4325
**Attribute für Standardabschnitt "**   
 ***Abschnitt* "ignoriert**  
  
 Sie können die Attribute eines Abschnitts standard nicht ändern. Zum Beispiel:  
  
```  
#pragma section(".sdata", long)  
```  
  
 Dies würde zu überschreiben die `.sdata` Standardabschnitt verwendet die **kurze** Datentyp mit der **lange** -Datentyp.  
  
 Standard-Abschnitten enthalten, deren Attribute nicht geändert werden dürfen,  
  
-   .Data  
  
-   ".sdata"  
  
-   ".BSS"  
  
-   .sbss  
  
-   .Text erstellen  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 Weitere Abschnitte können später hinzugefügt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [section](../../preprocessor/section.md)