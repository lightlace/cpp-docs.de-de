---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 4bf8f0c41e9ce3e296cf201efd4fd9be2033cbdb
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73702467"
---
# <a name="assume-32-bit-masm"></a>Annahme (32-Bit-MASM)

Aktiviert die Fehlerüberprüfung für Registerwerte. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> Angenommen, *segregister*:*Name* [[, *segregister*:*Name*]]...<br/>
> *Dataregiester*:*Type* [[, *dataregiester*:*Type*]]...<br/>
> *Register*: Error [[, *Register*: Error]]...<br/>
> [[*Register*:]] Nothing [[, *Register*: Nothing]]...

## <a name="remarks"></a>Hinweise

Nachdem ein `ASSUME` in Kraft gesetzt wurde, überwacht der Assembler Änderungen an den Werten der angegebenen Register. **Fehler** generiert einen Fehler, wenn das Register verwendet wird. **Nothing** entfernt die Register Fehlerüberprüfung nicht. Sie können verschiedene Arten von Annahmen in einer Anweisung kombinieren.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>