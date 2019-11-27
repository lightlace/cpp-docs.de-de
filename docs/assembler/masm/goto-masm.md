---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 424ff295fe37e7c5ff02897a01b99a7c75876f85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397479"
---
# <a name="goto-masm"></a>GOTO (MASM)

Überträgt die Assembly an die Zeile, die mit **:** _Macrolabel_gekennzeichnet ist.

## <a name="syntax"></a>Syntax

> **Goto** *makrolabel*

## <a name="remarks"></a>Hinweise

**Goto** ist nur innerhalb von [Makros](macro.md), [for](for-masm.md)-, [FORC](forc.md)-, [Repeat](repeat.md)-und [while](while-masm.md) -Blöcken zulässig. Das *Makro Label* -Ziel muss die einzige Anweisung in der Zeile sein, und es muss ein vorangestelltem Doppelpunkt vorangestellt sein.

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
