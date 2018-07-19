---
title: ML nicht schwerwiegende Fehler A2096 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e5d07afa864c9f6f4214de953aa9e03fe0e7e4f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053671"
---
# <a name="ml-nonfatal-error-a2096"></a>Nicht schwerwiegender ML-Fehler A2096
**Segment, eine Gruppe oder Segmentregister erwartet**  
  
 Ein Segment oder eine Gruppe wurde erwartet, aber wurde nicht gefunden.  
  
 Eine der folgenden aufgetreten ist:  
  
-   Der linke Operand mit dem Segment angegeben überschreiben-Operator (**:**) konnte sich nicht um ein Segment (CS, DS, SS, ES, FS oder GS), Gruppe RegisterName, Segmentnamen oder Segment Ausdruck.  
  
-   Die [VORAUSSETZEN](../../assembler/masm/assume.md) Richtlinie wurde ein Segment registrieren, ohne ein gültiges Segmentadresse, Segment registrieren, Gruppe oder die spezielle angegeben **Flatfile** Gruppe.  
  
## <a name="see-also"></a>Siehe auch  
 [ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)