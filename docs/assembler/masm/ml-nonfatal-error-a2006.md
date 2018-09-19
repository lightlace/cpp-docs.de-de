---
title: Schwerwiegender ML--Fehler A2006 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2006
dev_langs:
- C++
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f287c6ab46c6af71ba6dc0032f332ce3cc489454
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677404"
---
# <a name="ml-nonfatal-error-a2006"></a>Nicht schwerwiegender ML-Fehler A2006

**nicht definiertes Symbol: Bezeichner**

Es wurde versucht, ein Symbol verwenden, die nicht definiert wurde.

Eine der folgenden möglicherweise aufgetreten:

- Ein Symbol wurde nicht definiert.

- Ein Feld war nicht Mitglied der angegebenen Struktur.

- Ein Symbol wurde in einer Include-Datei definiert, die nicht enthalten ist.

- Ein externes Symbol wurde verwendet, ohne eine ["extern"](../../assembler/masm/extern-masm.md) oder [EXTERNDEF](../../assembler/masm/externdef.md) Richtlinie.

- Ein Symbolnamen wurde falsch geschrieben.

- Eine Bezeichnung lokaler Code wurde außerhalb ihres Bereichs auf die verwiesen wird.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>