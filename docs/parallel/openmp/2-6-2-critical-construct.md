---
title: 2.6.2 critical-Konstrukt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae7070fcc590307e71b0c34259bcbe1c12200550
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt
Die **kritische** Richtlinie identifiziert ein Konstrukt, die Ausführung des zugehörigen strukturierten Block auf einem einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der **kritische** Richtlinie lautet wie folgt:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 Ein optionales *Namen* kann verwendet werden, um die kritischen Bereichs zu identifizieren. Bezeichner, die zur Identifizierung einer kritischen Bereichs haben externe Verknüpfung und in einem Namespace von Namespaces, die von Bezeichnungen, Tags, Mitglieder und normale Bezeichner verwendet werden.  
  
 Ein Thread wartet am Anfang eines kritischen Bereichs, bis keine anderen Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten **kritische** Direktiven in den nicht angegebenen Namen zugeordnet.