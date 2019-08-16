---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: b793b3efa72a676b800c10b98ea06001ddcf10d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491437"
---
# <a name="fpo"></a>.FPO

Die. Die FPO-Direktive steuert die Ausgabe von debugdatensätzen in das Debug $ F-Segment bzw. den Abschnitt.

## <a name="syntax"></a>Syntax

> FPO (*cdwlocals*, *cdwpara AMS*, *cbprolog*, *cbregs*, *fuseebp*, *cbframe*)

### <a name="parameters"></a>Parameter

*cdwLocals*<br/>
Anzahl der lokalen Variablen, ein 32-Bit-Wert ohne Vorzeichen.

*cdwParams*<br/>
Die Größe der Parameter in DWords, ein 16-Bit-Wert ohne Vorzeichen.

*cbProlog*<br/>
Anzahl von Bytes im Prologcode der Funktion, ein 8-Bit-Wert ohne Vorzeichen.

*cbRegs*<br/>
Anzahl gespeicherter Nummern.

*fUseBP*<br/>
Gibt an, ob das EBP-Register zugeordnet wurde. entweder 0 oder 1.

*cbFrame*<br/>
Gibt den Rahmentyp an.  Weitere Informationen finden Sie unter [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
