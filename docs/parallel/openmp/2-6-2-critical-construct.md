---
title: 2.6.2 critical-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c658b32536404dde1a693582e78bfbedc2823b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt
Die **kritische** Richtlinie identifiziert ein Konstrukt, die Ausführung des zugehörigen strukturierten Block auf einem einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der **kritische** Richtlinie lautet wie folgt:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 Ein optionales *Namen* kann verwendet werden, um die kritischen Bereichs zu identifizieren. Bezeichner, die zur Identifizierung einer kritischen Bereichs haben externe Verknüpfung und in einem Namespace von Namespaces, die von Bezeichnungen, Tags, Mitglieder und normale Bezeichner verwendet werden.  
  
 Ein Thread wartet am Anfang eines kritischen Bereichs, bis keine anderen Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten **kritische** Direktiven in den nicht angegebenen Namen zugeordnet.