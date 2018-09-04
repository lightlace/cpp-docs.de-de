---
title: ALIAS (MASM) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- Alias
dev_langs:
- C++
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6a977d35040d8ca25cd3bd4ae4def233092b37a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691061"
---
# <a name="alias-masm"></a>ALIAS (MASM)

Die **ALIAS** Richtlinie erstellt einen alternativen Name für eine Funktion.  Dadurch können Sie mehrere Namen für eine Funktion erstellen, oder erstellen Sie Bibliotheken, die den Linker (LINK.exe) Zuordnen von einer alten Funktion in eine neue Funktion zu ermöglichen.

## <a name="syntax"></a>Syntax

> ALIAS \< *Alias*> = \< *tatsächliche-Name*>

#### <a name="parameters"></a>Parameter

*tatsächliche-name*<br/>
Der tatsächliche Name der Funktion oder Prozedur.  Die spitzen Klammern sind erforderlich.

*alias*<br/>
Der alternative oder Alias-Name.  Die spitzen Klammern sind erforderlich.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>