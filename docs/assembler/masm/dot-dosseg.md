---
title: .DOSSEG
ms.date: 08/30/2018
f1_keywords:
- .DOSSEG
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
ms.openlocfilehash: 28b3e351030ee83693c0fec5568aacf9b4b77c27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204360"
---
# <a name="dosseg"></a>.DOSSEG

Sortiert die Segmente gemäß der Konvention des MS-DOS-Segment an: CODE first, klicken Sie dann Segmente in nicht DGROUP, und klicken Sie dann die Segmente in DGROUP.

## <a name="syntax"></a>Syntax

> .DOSSEG

## <a name="remarks"></a>Hinweise

Die Segmente in DGROUP befolgen Sie diese Reihenfolge: Segmente nicht in BSS oder Stapel, und klicken Sie dann BSS-Segmente und schließlich STACK Segmente. In erster Linie verwendet dafür CodeView-Unterstützung in MASM eigenständige Programme. Identisch mit [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>