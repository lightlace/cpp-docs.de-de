---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: a03cbda5a8ff64f6c167766f416e7744a5382ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203079"
---
# <a name="goto-masm"></a>GOTO (MASM)

Überträgt die Assembly in die Zeile markiert **:**_Macrolabel_.

## <a name="syntax"></a>Syntax

> **GOTO** *macrolabel*

## <a name="remarks"></a>Hinweise

**"GoTo"** ist zulässig, nur in [MAKRO](macro.md), [für](for-masm.md), [Erzwungene](forc.md), [wiederholen](repeat.md), und [beim](while-masm.md)Blöcke. Die *Macrolabel* Ziel muss die einzige Anweisung in der Zeile sein und muss einen führenden Doppelpunkt vorangestellt werden.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
