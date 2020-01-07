---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: ec08be4941f81abed55420884b34dc817caf3f13
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317733"
---
# <a name="fpo-32-bit-masm"></a>. (32-Bit-MASM)

Die **. Die FPO** -Direktive steuert die Ausgabe von debugdatensätzen in das Debug $ F-Segment bzw. den Abschnitt. (nur 32-Bit-MASM.)

## <a name="syntax"></a>Syntax

> **. FPO** (*cdwlocals*, *cdwpara AMS*, *cbprolog*, *cbregs*, *fuseebp*, *cbframe*)

### <a name="parameters"></a>Parameters

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

[Direktivenverweis](directives-reference.md)\
[MASM-BNF-Grammatik](masm-bnf-grammar.md)
