---
title: Schwerwiegender ML--Fehler A2066 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2066
dev_langs:
- C++
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cf5cbe7d5c77da7f129cbc40ffa97f4051afca6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690251"
---
# <a name="ml-nonfatal-error-a2066"></a>Nicht schwerwiegender ML-Fehler A2066

**CPU-Modus und Segment Größe nicht kompatibel**

Es wurde versucht, öffnen Sie ein Segment mit einer **USE16**, **USE32**, oder **Flatfile** -Attribut, das nicht mit den angegebenen CPU- oder So ändern Sie in eine 16-Bit-CPU in eine 32-Bit-kompatibel war Segment.

Die **USE32** und **Flatfile** Attribute müssen durch die.386 oder höher Prozessor-Anweisung stehen.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>