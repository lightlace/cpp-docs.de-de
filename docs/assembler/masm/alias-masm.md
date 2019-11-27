---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 274ac451005015b2693d8674673af574ec781bdc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399291"
---
# <a name="alias-masm"></a>ALIAS (MASM)

Die **Alias** -Direktive erstellt einen alternativen Namen für eine Funktion.  Auf diese Weise können Sie mehrere Namen für eine Funktion erstellen oder Bibliotheken erstellen, mit denen der Linker (Link. exe) eine alte Funktion einer neuen Funktion zuordnen kann.

## <a name="syntax"></a>Syntax

> **Alias \<** _Alias_ **> = \<** _tatsächlicher Name_ **>**

#### <a name="parameters"></a>Parameter

*tatsächlicher Name*\
Der tatsächliche Name der Funktion oder Prozedur.  Die Klammern sind erforderlich.

*Alias*\
Der Alternative oder Alias Name.  Die Klammern sind erforderlich.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
