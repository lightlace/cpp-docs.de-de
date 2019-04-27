---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 30d1b3ae7c6676aeb97b91c7627da859525b9ce1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203614"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Definiert eine oder mehrere externe Variablen, Bezeichnungen oder Symbole, so genannte *Namen* , dessen Typ *Typ*.

## <a name="syntax"></a>Syntax

> "Extern" [[*Langtype*]] *Namen* [[(*Altid*)]]: *Typ* [[, [[*Langtype*]]  *Namen* [[(*Altid*)]]: *Typ*]]...

## <a name="remarks"></a>Hinweise

Die *Typ* kann [ABS](../../assembler/masm/operator-abs.md), welche Importe *Namen* als Konstante. Identisch mit [EXTRN](../../assembler/masm/extrn.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>