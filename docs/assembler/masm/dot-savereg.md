---
title: . SAVEREG | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEREG
dev_langs:
- C++
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7010664cd2e80841d9e35d8fcf72d195cecf796
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688988"
---
# <a name="savereg"></a>.SAVEREG

Generiert Sie entweder eine `UWOP_SAVE_NONVOL` oder `UWOP_SAVE_NONVOL_FAR` Entladen von Codeeintrag für den angegebenen Register (`reg`) und Offset (`offset`) mit den aktuellen Prologoffset. Die effizienteste Codierung wählen MASM.

## <a name="syntax"></a>Syntax

> . SAVEREG Reg, offset

## <a name="remarks"></a>Hinweise

. SAVEREG ist nur zulässig, in der Prolog, die von erweitert und ermöglicht ml64.exe angeben, wie eine Funktion des Frames entlädt die [PROC](../../assembler/masm/proc.md) FRAME-Deklaration, um die [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) Richtlinie. Diese Direktiven generieren Sie Code nicht; Generieren sie nur `.xdata` und `.pdata`. . Indem Sie die Anweisungen, die die Aktionen, entladen werden implementieren, sollte SAVEREG vorangestellt werden. Es hat sich bewährt, sowohl den Code, den sie auf die Entladung in einem Makro gedacht sind, um sicherzustellen, dass Vereinbarung als auch die Entladung Anweisungen zu umschließen.

Weitere Informationen finden Sie unter [MASM für X64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>