---
title: Kommentare (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a873ca82fc51c2f08e3788f9ec3c59c199961105
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111874"
---
# <a name="comments-c"></a>Kommentare (C++)

Ein Kommentar ist Text, den der Compiler ignoriert, der jedoch für Programmierer hilfreich ist. Kommentare werden in der Regel verwendet, um Code zu Referenzzwecken mit Anmerkungen zu versehen. Der Compiler behandelt sie als Leerzeichen. Sie können Kommentare beim Testen verwenden, um bestimmte Codezeilen als inaktiv zu markieren; allerdings `#if` / `#endif` -präprozessoranweisungen besser dafür da können Sie Code, der Kommentare enthält umgeben, aber Kommentare nicht schachteln.

Es gibt folgende Möglichkeiten, einen C++-Kommentar zu schreiben:

- Die Zeichen `/*` (Schrägstrich, Sternchen), gefolgt von einer beliebigen Folge von Zeichen (einschließlich neuer Zeilen), gefolgt von den Zeichen `*/`. Diese Syntax ist mit der Syntax von ANSI C identisch.

- Die Zeichen `//` (zwei Schrägstriche), gefolgt von einer beliebigen Folge von Zeichen. Eine neue Zeile, der nicht direkt ein umgekehrter Schrägstrich vorangestellt ist, beendet diese Art des Kommentars. Daher wird dies häufig als "einzeiliger Kommentar" bezeichnet.

Die Kommentarzeichen (`/*`, `*/` und `//`) verfügen über keine besondere Bedeutung innerhalb einer Zeichenkonstante, eines Zeichenfolgenliterals oder eines Kommentars. Kommentare, die die erste Syntax verwenden, können deshalb nicht geschachtelt werden.

## <a name="see-also"></a>Siehe auch

[Lexikalische Konventionen](../cpp/lexical-conventions.md)