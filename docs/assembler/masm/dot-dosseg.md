---
title: . DOSSEG | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .DOSSEG
dev_langs:
- C++
helpviewer_keywords:
- .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee0b0b049ece65786c4d4857c2e082a067fee4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693231"
---
# <a name="dosseg"></a>.DOSSEG

Sortiert die Segmente gemäß der Konvention des MS-DOS-Segment: CODE zuerst dann nicht in DGROUP Segmente, und klicken Sie dann im DGROUP Segmente.

## <a name="syntax"></a>Syntax

> .DOSSEG

## <a name="remarks"></a>Hinweise

Die Segmente in DGROUP befolgen Sie diese Reihenfolge: Segmente nicht in BSS oder Stapel, und klicken Sie dann BSS-Segmente und schließlich STACK Segmente. In erster Linie verwendet dafür CodeView-Unterstützung in MASM eigenständige Programme. Identisch mit [DOSSEG](../../assembler/masm/dosseg.md).

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>