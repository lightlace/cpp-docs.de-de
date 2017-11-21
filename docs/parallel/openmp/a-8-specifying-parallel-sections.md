---
title: A.8, parallele Abschnitte angeben | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d369c2e3a0d326ab4c835a30681f3dbe50f789f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Angeben von parallelen Abschnitten
Im folgenden Beispiel (für [Abschnitt 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) auf der Seite "14") Funktionen *Xaxis*, *Yaxis*, und *Zaxis* gleichzeitig ausgeführt werden können. Die erste `section` Richtlinie ist optional.  Beachten Sie, dass alle `section` Richtlinien müssen in der lexikalische Wertebereich angezeigt werden die `parallel sections` erstellen.  
  
```  
#pragma omp parallel sections  
{  
    #pragma omp section  
        xaxis();  
    #pragma omp section  
        yaxis();  
    #pragma omp section  
        zaxis();  
}  
```