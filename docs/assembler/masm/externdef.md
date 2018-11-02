---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 23d34af470e825a8535de8cb28645a7bfb4c4d1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619764"
---
# <a name="externdef"></a>EXTERNDEF

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole, so genannte *Namen* , dessen Typ `type`.

## <a name="syntax"></a>Syntax

> Namenstyp: EXTERNDEF [[Langtype]] [[, [[Langtype]]-Name: Typ]]...

## <a name="remarks"></a>Hinweise

Wenn *Namen* definiert ist im Modul, wird er als behandelt [öffentliche](../../assembler/masm/public-masm.md). Wenn *Namen* verwiesen wird im Modul, wird er als behandelt ["extern"](../../assembler/masm/extern-masm.md). Wenn *Namen* ist nicht auf die verwiesen wird, wird Sie ignoriert. Die `type` kann [ABS](../../assembler/masm/operator-abs.md), welche Importe *Namen* als Konstante. In der Regel verwendet Dateien einschließt.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>