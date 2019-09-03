---
title: '##ifdef- und #ifndef-Anweisungen (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#ifndef'
- '#ifdef'
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
ms.openlocfilehash: 433076388f3646b19d75a907c6b2254098096688
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220114"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef-und #ifndef Direktiven (C++C/)

Die Anweisungen **#ifdef** und **#ifndef** haben dieselbe Auswirkung wie die [#if](hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md) -Direktive, wenn Sie mit dem **definierten** Operator verwendet wird.

## <a name="syntax"></a>Syntax

> **#ifdef** *Bezeichner*\
> **#ifndef** *Bezeichner*

Diese Direktiven sind äquivalent zu:

> **#if definiert** *Bezeichner*\
> **#if! definiert** *Bezeichner*

## <a name="remarks"></a>Hinweise

Sie können die **#ifdef** -und **#ifndef** Direktiven `#if` verwenden, die überall verwendet werden können. Die **#ifdef** *Identifier* -Anweisung entspricht, `#if 1` wenn der Bezeichner definiert wurde. Dies entspricht dem Zeitpunkt `#if 0` , an dem der Bezeichner nicht definiert wurde oder durch die `#undef` -Direktive nicht definiert wurde. Diese Anweisungen überprüfen lediglich, ob die mit `#define` definierten Bezeichner vorhanden sind, und nicht, ob Bezeichner vorhanden sind, die im C- oder C++-Quellcode deklariert werden.

Diese Anweisungen werden nur bereitgestellt, um die Kompatibilität mit früheren Versionen der Sprache zu gewährleisten. Der **definierte (** *Bezeichner* **)** Konstante Ausdruck, der `#if` mit der Direktive verwendet wird, wird bevorzugt.

Die **#ifndef** -Direktive prüft das Gegenteil der durch **#ifdef**geprüften Bedingung. Wenn der Bezeichner nicht definiert wurde oder seine Definition mit `#undef`entfernt wurde, ist die Bedingung "true" (ungleich null). Andernfalls ist die Bedingung "false" (0).

**Microsoft-spezifisch**

Der *Bezeichner* kann mithilfe der [/D](../build/reference/d-preprocessor-definitions.md) -Option von der Befehlszeile aus übermittelt werden. Bis zu 30 Makros können mit `/D`angegeben werden.

Die **#ifdef** -Direktive ist nützlich, um zu überprüfen, ob eine Definition vorhanden ist, da eine Definition von der Befehlszeile aus übermittelt werden kann. Beispiel:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
