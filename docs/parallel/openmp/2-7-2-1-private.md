---
title: 2.7.2.1 private | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d06650a784b5b59405f446f4701918393b21fa3b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387236"
---
# <a name="2721-private"></a>2.7.2.1 private

Die `private` -Klausel deklariert, die Variablen im Variable-Liste für jeden Thread in einem Team privat sein. Die Syntax der `private` -Klausel ist wie folgt:

```
private(variable-list)
```

Das Verhalten einer Variablen angegeben, die einem `private` -Klausel ist wie folgt. Für das Konstrukt wird ein neues Objekt mit automatischer Speicherdauer zugeordnet. Die Größe und Ausrichtung des neuen Objekts werden durch den Typ der Variablen bestimmt. Die Reservierung erfolgt einmal für jeden Thread im Team, und ein Standardkonstruktor wird aufgerufen, für ein Klassenobjekt bei Bedarf; Andernfalls ist der Anfangswert unbestimmt.  Das ursprüngliche Objekt, das die Variable verweist hat einen unbestimmten Wert beim Einstieg in das Konstrukt, darf nicht geändert werden, in der dynamischen Wertebereich des Konstrukts und verfügt über einen unbestimmten Wert nach dem Verlassen des Konstrukts.

Im lexikalischen Block des Konstrukts die Richtlinie verweist die Variable die neue private-Objekt, die vom Thread zugeordnet.

Die Einschränkungen fest, die `private` Klausel lauten wie folgt:

- Eine Variable mit einem Klassentyp, der im angegebenen ein `private` Klausel muss einen erreichbare, eindeutige Standardkonstruktor verfügen.

- Eine Variable, die im angegebenen ein `private` Klausel darf keine **const**-Typ qualifiziert, es sei denn, sie eine Klasse, und geben Sie einen `mutable` Member.

- Eine Variable, die im angegebenen ein `private` Klausel darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Variablen in der `reduction` -Klausel einer **parallele** Richtlinie kann nicht angegeben werden, eine `private` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.