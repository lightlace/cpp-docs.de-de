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
ms.openlocfilehash: 6fbba50e56ae06dc3afb64582d4a131bba75a6c8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055852"
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