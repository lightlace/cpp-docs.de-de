---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 8f0388c3df9804c0cdb105162a962a44fe207345
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703310"
---
# <a name="dosseg-32-bit-masm"></a>. Dosseg (32-Bit-MASM)

Sortiert die Segmente gemäß der MS-DOS-Segment Konvention: Code First, dann Segmente nicht in DGROUP und dann Segmente in DGROUP. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> .DOSSEG

## <a name="remarks"></a>Hinweise

Die Segmente in der DGROUP Folgen der folgenden Reihenfolge: Segmente, die nicht in BSS oder Stapel enthalten sind, dann BSS-Segmente und schließlich Stapel Segmente. Wird hauptsächlich zum Sicherstellen der CodeView-Unterstützung in eigenständigen MASM-Programmen verwendet. Identisch mit [dosseg](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>