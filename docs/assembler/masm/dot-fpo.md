---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 650c69be17c9271c343360edbb90f093841a1047
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398255"
---
# <a name="fpo-32-bit-masm"></a>. (32-Bit-MASM)

Die **. Die FPO** -Direktive steuert die Ausgabe von debugdatensätzen in das Debug $ F-Segment bzw. den Abschnitt. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **. FPO** (*cdwlocals*, *cdwpara AMS*, *cbprolog*, *cbregs*, *fuseebp*, *cbframe*)

### <a name="parameters"></a>Parameter

*cdwlocals* -\
Anzahl der lokalen Variablen, ein 32-Bit-Wert ohne Vorzeichen.

*cdwpara*\
Die Größe der Parameter in DWords, ein 16-Bit-Wert ohne Vorzeichen.

*cbprolog* -\
Anzahl von Bytes im Prologcode der Funktion, ein 8-Bit-Wert ohne Vorzeichen.

*cbregs* -\
Anzahl gespeicherter Nummern.

*fuberbp* -\
Gibt an, ob das EBP-Register zugeordnet wurde. entweder 0 oder 1.

*cbframe* -\
Gibt den Rahmentyp an.  Weitere Informationen finden Sie unter [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) .

## <a name="see-also"></a>Siehe auch

[Direktivenverweis](directives-reference.md)
