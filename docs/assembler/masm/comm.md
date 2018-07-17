---
title: COMM | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1df6c729ab130a7ff38d7f7cf83224e7425e7dba
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="comm"></a>COMM

Erstellt eine Internetcafés Variable mit den Attributen, die im angegebenen *Definition*.

## <a name="syntax"></a>Syntax

> **COMM** *Definition* [, *Definition*]...

## <a name="remarks"></a>Hinweise

Internetcafés Variablen werden vom Linker zugeordnet und können nicht initialisiert werden. Dies bedeutet, dass der Speicherort oder eine Sequenz solcher Variablen abhängen dürfen.

Jede *Definition* weist folgende Form:

[*Langtype*] [**NEAR** &#124; **FAR**] _Bezeichnung_**:**_Typ_[**:**_Anzahl_]

Das optionale *Langtype* legt die Benennungskonventionen für folgende Name. Jeder angegebene Sprache überschreibt die **. Modell** Richtlinie. Das optionale **NEAR** oder **FAR** Überschreiben des aktuellen Modells von Arbeitsspeicher. Die *Bezeichnung* ist der Name der Variablen. Die *Typ* kann einem beliebigen Typspezifizierer ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)usw.) oder eine ganze Zahl, die die Anzahl von Bytes angibt. Das optionale *Anzahl* gibt die Anzahl der Elemente in das deklarierte Objekt; der Standardwert ist 1.

## <a name="example"></a>Beispiel

Dieses Beispiel erstellt ein Array von 512-BYTE-Elemente:

```masm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)
