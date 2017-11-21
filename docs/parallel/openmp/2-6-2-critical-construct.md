---
title: 2.6.2 critical-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13e9b4a8611732c7dddb81be1ca6123b725f7169
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt
Die **kritische** Richtlinie identifiziert ein Konstrukt, die Ausführung des zugehörigen strukturierten Block auf einem einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der **kritische** Richtlinie lautet wie folgt:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 Ein optionales *Namen* kann verwendet werden, um die kritischen Bereichs zu identifizieren. Bezeichner, die zur Identifizierung einer kritischen Bereichs haben externe Verknüpfung und in einem Namespace von Namespaces, die von Bezeichnungen, Tags, Mitglieder und normale Bezeichner verwendet werden.  
  
 Ein Thread wartet am Anfang eines kritischen Bereichs, bis keine anderen Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten **kritische** Direktiven in den nicht angegebenen Namen zugeordnet.