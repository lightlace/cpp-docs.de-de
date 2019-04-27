---
title: ALIAS (MASM)
ms.date: 08/30/2018
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: ab00092f410d34119e876db4562e6d0709743d79
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166489"
---
# <a name="alias-masm"></a>ALIAS (MASM)

Die **ALIAS** Richtlinie erstellt einen alternativen Name für eine Funktion.  Dadurch können Sie mehrere Namen für eine Funktion erstellen, oder erstellen Sie Bibliotheken, die den Linker (LINK.exe) Zuordnen von einer alten Funktion in eine neue Funktion zu ermöglichen.

## <a name="syntax"></a>Syntax

> ALIAS \<*alias*> = \<*actual-name*>

#### <a name="parameters"></a>Parameter

*actual-name*<br/>
Der tatsächliche Name der Funktion oder Prozedur.  Die spitzen Klammern sind erforderlich.

*alias*<br/>
Der alternative oder Alias-Name.  Die spitzen Klammern sind erforderlich.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>