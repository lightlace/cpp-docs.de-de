---
title: "\"GOTO\" (MASM) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0be678e2d39389cbc551c386c1890f799124b5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43694003"
---
# <a name="goto-masm"></a>GOTO (MASM)

Überträgt die Assembly in die Zeile markiert **:**_Macrolabel_.

## <a name="syntax"></a>Syntax

> **"GoTo"** *Macrolabel*

## <a name="remarks"></a>Hinweise

**"GoTo"** ist zulässig, nur in [MAKRO](macro.md), [für](for-masm.md), [Erzwungene](forc.md), [wiederholen](repeat.md), und [beim](while-masm.md)Blöcke. Die *Macrolabel* Ziel muss die einzige Anweisung in der Zeile sein und muss einen führenden Doppelpunkt vorangestellt werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
