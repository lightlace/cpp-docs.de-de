---
title: ANGENOMMEN | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0e43548292d2ffecbebdaead6aa12d6dacc352
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693807"
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