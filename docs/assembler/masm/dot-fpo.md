---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3938d9194c35d567ea670e0b92a731193ccd2254
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703799"
---
# <a name="fpo-32-bit-masm"></a>. (32-Bit-MASM)

Die. Die FPO-Direktive steuert die Ausgabe von debugdatensätzen in das Debug $ F-Segment bzw. den Abschnitt. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> FPO (*cdwlocals*, *cdwpara AMS*, *cbprolog*, *cbregs*, *fuseebp*, *cbframe*)

### <a name="parameters"></a>Parameter

*cdwlocals*<br/>
Anzahl der lokalen Variablen, ein 32-Bit-Wert ohne Vorzeichen.

*cdwparametriams*<br/>
Die Größe der Parameter in DWords, ein 16-Bit-Wert ohne Vorzeichen.

*cbprolog*<br/>
Anzahl von Bytes im Prologcode der Funktion, ein 8-Bit-Wert ohne Vorzeichen.

*cbregs*<br/>
Anzahl gespeicherter Nummern.

*fuabbp*<br/>
Gibt an, ob das EBP-Register zugeordnet wurde. entweder 0 oder 1.

*cbframe*<br/>
Gibt den Rahmentyp an.  Weitere Informationen finden Sie unter [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
