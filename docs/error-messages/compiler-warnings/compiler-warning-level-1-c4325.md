---
title: Compilerwarnung (Stufe 1) C4325 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab31150efc02601d7392470198e162e979ac4917
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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