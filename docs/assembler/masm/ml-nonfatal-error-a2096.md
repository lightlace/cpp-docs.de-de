---
title: ML nicht schwerwiegende Fehler A2096 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2096
dev_langs: C++
helpviewer_keywords: A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d4466d87e33068b10b3f620bfbe764e4aec76c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2096"></a>Nicht schwerwiegender ML-Fehler A2096
**Segment, eine Gruppe oder Segmentregister erwartet**  
  
 Ein Segment oder eine Gruppe wurde erwartet, aber wurde nicht gefunden.  
  
 Eine der folgenden aufgetreten ist:  
  
-   Der linke Operand mit dem Segment angegeben überschreiben-Operator (**:**) konnte sich nicht um ein Segment (CS, DS, SS, ES, FS oder GS), Gruppe RegisterName, Segmentnamen oder Segment Ausdruck.  
  
-   Die [VORAUSSETZEN](../../assembler/masm/assume.md) Richtlinie wurde ein Segment registrieren, ohne ein gültiges Segmentadresse, Segment registrieren, Gruppe oder die spezielle angegeben **Flatfile** Gruppe.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)