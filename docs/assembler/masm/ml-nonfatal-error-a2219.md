---
title: Nicht schwerwiegender ML-Fehler A2219
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: 61fa6bc6d630f1e8a8ac84492b60690c9545fb3e
ms.sourcegitcommit: 79e985d3c6e8ccaf94f6e641972887cae8c6eeb0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66197679"
---
# <a name="ml-nonfatal-error-a2219"></a>Nicht schwerwiegender ML-Fehler A2219

> Fehlerhafte Ausrichtung für den Offset in entladungscode

## <a name="remarks"></a>Hinweise

Der Operand für [ &period;ALLOCSTACK](../../assembler/masm/dot-allocstack.md) und [ &period;SAVEREG](../../assembler/masm/dot-savereg.md) muss ein Vielfaches von 8 sein.  Der Operand für [ &period;SAVEXMM128](../../assembler/masm/dot-savexmm128.md) und [ &period;SETFRAME](../../assembler/masm/dot-setframe.md) muss ein Vielfaches von 16 sein.

## <a name="see-also"></a>Siehe auch

[ML-Fehlermeldungen](../../assembler/masm/ml-error-messages.md)
