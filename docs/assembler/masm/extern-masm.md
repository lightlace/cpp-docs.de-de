---
title: EXTERN (MASM) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a9008e8c1153c0a9b06530b14e661436f7e62a9
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693669"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole, so genannte *Namen* , dessen Typ *Typ*.

## <a name="syntax"></a>Syntax

> "Extern" [[*Langtype*]] *Namen* [[(*Altid*)]]: *Typ* [[, [[*Langtype*]]  *Namen* [[(*Altid*)]]: *Typ*]]...

## <a name="remarks"></a>Hinweise

Die *Typ* kann [ABS](../../assembler/masm/operator-abs.md), welche Importe *Namen* als Konstante. Identisch mit [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>