---
title: PROTO
ms.date: 10/22/2018
f1_keywords:
- PROTO
helpviewer_keywords:
- PROTO directive
ms.assetid: 0487ee16-9dc7-43d1-9445-cd1601f5a080
ms.openlocfilehash: 616b6be2a5c191ebc67d61288cb5fa6c183091fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210520"
---
# <a name="proto"></a>PROTO

Prototypen, einer Funktion oder Prozedur. Sie können die Funktion aufrufen Prototyp von PROTO-Anweisung mithilfe der [INVOKE](invoke.md) Richtlinie.

## <a name="syntax"></a>Syntax

> *Bezeichnung* **PROTO** \[ *Abstand*] \[ *Langtype*] \[ __,__ \[ *Parameter*]__:__*Tag*]...

### <a name="parameters"></a>Parameter

*label*<br/>
Der Name der Prototyp-Funktion.

*distance*<br/>
(Optional) In 16-Bit-Memory-Modellen verwendet, um die Standardeinstellung überschreiben, und geben Sie an **NEAR** oder **weit** aufrufen.

*langtype*<br/>
(Optional) Legt die aufrufende und der Name-Konvention für die Prozeduren und die öffentlichen Symbole fest. Unterstützten Konventionen sind:

- 32-Bit- **Flatfile** Modell: **C**, **STDCALL**

- 16-Bit-Modelle: **C**, **BASIC**, **FORTRAN**, **PASCAL**, **SYSCALL**, **STDCALL**

*parameter*<br/>
Der optionale Name für einen Funktionsparameter.

*tag*<br/>
Der Typ eines Funktionsparameters.

Die *Parameter* und *Tag* Parameter können mehrfach vorkommen, einmal für jede übergebene Argument.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt eine **PROTO** Deklaration für eine Funktion namens `addup3` , verwendet eine **NEAR** Aufruf zum Überschreiben des Standardwerts 16-Bit-Modell für die Prozeduraufrufen, und verwendet die **C**Aufrufkonvention für die stack-Parameter und Rückgabewerte. Es akzeptiert zwei Argumente: ein **WORD** und **VARARG**.

```MASM
addup3 PROTO NEAR C, argcount:WORD, arg1:VARARG
```

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](directives-reference.md)<br/>
[. Referenz-OBJEKTMODELL](dot-model.md)<br/>
