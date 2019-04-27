---
title: COMM
ms.date: 08/30/2018
f1_keywords:
- COMM
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
ms.openlocfilehash: 342c8acd95fd45de1a21dc298325de9a7b40b717
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179106"
---
# <a name="comm"></a>COMM

Erstellt eine kommunales Variable mit den Attributen, die im angegebenen *Definition*.

## <a name="syntax"></a>Syntax

> **COMM** *Definition* [, *Definition*]...

## <a name="remarks"></a>Hinweise

Kommunales Variablen werden durch den Linker zugeordnet und können nicht initialisiert werden. Dies bedeutet, dass Sie auf den Speicherort oder eine Sequenz solcher Variablen abhängen dürfen.

Jede *Definition* hat folgendes Format:

[*Langtype*] [**NEAR** &#124; **weit**] _Bezeichnung_**:**_Typ_[**:**_Anzahl_]

Der optionale *Langtype* legt die Namenskonventionen der folgende Name. Überschreibt es mit einer beliebigen Sprache gemäß der **. Modell** Richtlinie. Der optionale **NEAR** oder **weit** Überschreiben der aktuellen Speichermodell. Die *Bezeichnung* ist der Name der Variablen. Die *Typ* kann einem beliebigen Typspezifizierer sein ([BYTE](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)usw.) oder eine ganze Zahl, die die Anzahl von Bytes angibt. Der optionale *Anzahl* gibt die Anzahl der Elemente in das deklarierte Objekt; der Standardwert ist 1.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Array von 512-BYTE-Elementen erstellt:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
