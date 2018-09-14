---
title: . WIEDERHOLEN SIE DIE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8856ed0e1d86277a413baac2c56e5c5ca2ea9ff0
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "43687951"
---
# <a name="repeat"></a>.REPEAT

Generiert Code, durch die Ausführung des Blocks von wiederholt *Anweisungen* bis `condition` wird "true". [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md), wenn CX 0 (null), ist "true" wird möglicherweise durch ersetzt [. BIS](../../assembler/masm/dot-until.md). Die `condition` ist optional, mit **. UNTILCXZ**.

## <a name="syntax"></a>Syntax

> .REPEAT<br/>
> Anweisungen<br/>
> . BIS Bedingung

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>