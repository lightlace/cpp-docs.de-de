---
title: EXTERNDEF | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- EXTERNDEF
dev_langs:
- C++
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5c3d42cabb88c38ce1d98da24cd2cb4ddec8d5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683660"
---
# <a name="externdef"></a>EXTERNDEF

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole, so genannte *Namen* , dessen Typ `type`.

## <a name="syntax"></a>Syntax

> Namenstyp: EXTERNDEF [[Langtype]] [[, [[Langtype]]-Name: Typ]]...

## <a name="remarks"></a>Hinweise

Wenn *Namen* definiert ist im Modul, wird er als behandelt [öffentliche](../../assembler/masm/public-masm.md). Wenn *Namen* verwiesen wird im Modul, wird er als behandelt ["extern"](../../assembler/masm/extern-masm.md). Wenn *Namen* ist nicht auf die verwiesen wird, wird Sie ignoriert. Die `type` kann [ABS](../../assembler/masm/operator-abs.md), welche Importe *Namen* als Konstante. In der Regel verwendet Dateien einschließt.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>