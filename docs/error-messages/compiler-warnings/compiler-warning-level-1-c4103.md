---
title: "Compilerwarnung (Stufe 1) C4103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4103"
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Dateiname': Ausrichtung wurde nach Einschließen des Headers geändert, möglicherweise fehlt \#pragma pack\(pop\)  
  
 Die Ausrichtung hat Auswirkungen auf das Klassenlayout, und wenn die Ausrichtung in mehreren Headerdateien unterschiedlich ist, treten im Allgemeinen Probleme auf.  
  
 Verwenden Sie \#pragma [pack](../../preprocessor/pack.md)\(pop\), bevor Sie die Headerdatei verlassen, um diese Warnung zu vermeiden.  
  
 Im folgenden Beispiel wird C4103 generiert:  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 und anschließend  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```