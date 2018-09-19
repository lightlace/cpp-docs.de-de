---
title: Schwerwiegender ML--Fehler A2219 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2219
dev_langs:
- C++
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 365997181b0d4f4471162d7cf8f65a4429e69e74
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681644"
---
# <a name="ml-nonfatal-error-a2219"></a>Nicht schwerwiegender ML-Fehler A2219

**Fehlerhafte Ausrichtung für den Offset in entladungscode**

Der Operand für [. ALLOCSTACK](../../assembler/masm/dot-allocstack.md) und [. SAVEREG](../../assembler/masm/dot-savereg.md) muss ein Vielfaches von 8 sein.  Der Operand für [. SAVEXMM128](../../assembler/masm/dot-savexmm128.md) und [. SETFRAME](../../assembler/masm/dot-setframe.md) muss ein Vielfaches von 16 sein.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)<br/>