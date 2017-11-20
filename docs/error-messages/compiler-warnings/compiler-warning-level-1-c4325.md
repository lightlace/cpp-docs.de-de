---
title: Compilerwarnung (Stufe 1) C4325 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4325
dev_langs: C++
helpviewer_keywords: C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b5ce2e90705a1f3a899ef31313d1a402d2ecc04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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