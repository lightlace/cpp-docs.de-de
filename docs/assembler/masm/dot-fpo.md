---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3bdb6af98aa71fef3d4af24091dc7463d917ce15
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915959"
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
Gibt den Rahmentyp an.  Weitere Informationen finden Sie unter [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
