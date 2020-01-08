---
title: .DOSSEG
ms.date: 11/05/2019
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: e27b0ae185542c11ee29119575d5c8225501f71e
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313846"
---
# <a name="dosseg-32-bit-masm"></a>. Dosseg (32-Bit-MASM)

Sortiert die Segmente gemäß der MS-DOS-Segment Konvention: Code First, dann Segmente nicht in DGROUP und dann Segmente in DGROUP. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **.DOSSEG**

## <a name="remarks"></a>Hinweise

Die Segmente in der DGROUP Folgen der folgenden Reihenfolge: Segmente, die nicht in BSS oder Stapel enthalten sind, dann BSS-Segmente und schließlich Stapel Segmente. Wird hauptsächlich zum Sicherstellen der CodeView-Unterstützung in eigenständigen MASM-Programmen verwendet. Identisch mit [dosseg](dosseg.md).

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
