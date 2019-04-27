---
title: ASSUME
ms.date: 08/30/2018
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 97a57cc8a1acccf70572ff963e496aa79fa3ab43
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166463"
---
# <a name="assume"></a>ASSUME

Fehler beim Überprüfen auf Registerwerte wird aktiviert.

## <a name="syntax"></a>Syntax

> ASSUME *Segregister*:*Namen* [[, *Segregister*:*Namen*]]...<br/>
> ASSUME *Dataregister*:*Typ* [[, *Dataregister*:*Typ*]]...<br/>
> ASSUME *registrieren*: Fehler [[, *registrieren*: Fehler]]...<br/>
> ASSUME [[*registrieren*:]] "NOTHING" [[, *registrieren*: "NOTHING"]]...

## <a name="remarks"></a>Hinweise

Nach einer `ASSUME` ist in Kraft getreten, die Assembler achtet auf die Werte der angegebenen Register. **Fehler** wird ein Fehler generiert, wenn das Register verwendet wird. **"NOTHING"** entfernt fehlerüberprüfung zu registrieren. Sie können verschiedene Arten von Annahmen, die in einer einzigen Anweisung kombinieren.

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>