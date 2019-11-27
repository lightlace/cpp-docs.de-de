---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 17edea122afc03a8c3a2fdc86ee6c06c2ccf3c85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398489"
---
# <a name="dosseg-32-bit-masm"></a>. Dosseg (32-Bit-MASM)

Sortiert die Segmente gemäß der MS-DOS-Segment Konvention: Code First, dann Segmente nicht in DGROUP und dann Segmente in DGROUP. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **.DOSSEG**

## <a name="remarks"></a>Hinweise

Die Segmente in der DGROUP Folgen der folgenden Reihenfolge: Segmente, die nicht in BSS oder Stapel enthalten sind, dann BSS-Segmente und schließlich Stapel Segmente. Wird hauptsächlich zum Sicherstellen der CodeView-Unterstützung in eigenständigen MASM-Programmen verwendet. Identisch mit [dosseg](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
