---
title: '#Ifdef- und #ifndef-Direktiven (C/C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1ba603941b5d08bc56d8385f2b721fb1bef6586
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075891"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef- und #ifndef-Anweisungen (C/C++)
Die **#ifdef** und **#ifndef** Anweisungen führen Sie die gleiche Aufgabe wie die `#if` Richtlinie, die bei einer Verwendung mit **definiert**( *Bezeichner* ).

## <a name="syntax"></a>Syntax

```
#ifdef identifier
#ifndef identifier

// equivalent to
#if defined identifier
#if !defined identifier
```

## <a name="remarks"></a>Hinweise

Können Sie die **#ifdef** und **#ifndef** Direktiven an einer beliebigen Stelle `#if` kann verwendet werden. Die **#ifdef** *Bezeichner* Anweisung entspricht `#if 1` beim *Bezeichner* definiert wurde, und dies ist äquivalent zum `#if 0` beim *Bezeichner* wurde nicht definiert oder wurde nicht definiert wurde, mit der `#undef` Richtlinie. Diese Anweisungen überprüfen lediglich, ob die mit `#define` definierten Bezeichner vorhanden sind, und nicht, ob Bezeichner vorhanden sind, die im C- oder C++-Quellcode deklariert werden.

Diese Anweisungen werden nur bereitgestellt, um die Kompatibilität mit früheren Versionen der Sprache zu gewährleisten. Die **definiert (** *Bezeichner* **)** konstanter Ausdruck, der Verwendung der `#if` Richtlinie wird bevorzugt.

Die **#ifndef** Richtlinie überprüft das Gegenteil der Bedingung, die von überprüften **#ifdef**. Wenn der Bezeichner nicht definiert wurde (oder ihre Definition mit `#undef` entfernt wurde), ist die Bedingung "true" (ungleich 0). Andernfalls ist die Bedingung "false" (0).

**Microsoft-spezifisch**

Die *Bezeichner* übergeben werden kann, über die Befehlszeile mit der `/D` Option. Bis zu 30 Makros kann angegeben werden, mit `/D`.

Dies ist hilfreich, wenn überprüft werden soll, ob eine Definition vorhanden ist, da diese von der Befehlszeile übergeben werden kann. Zum Beispiel:

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