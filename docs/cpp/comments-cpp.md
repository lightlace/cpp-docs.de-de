---
title: Kommentare (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: a90d9d37e69cb2e8be4ab18f77026fdce1221307
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399173"
---
# <a name="comments-c"></a>Kommentare (C++)

Ein Kommentar ist Text, den der Compiler ignoriert, der jedoch für Programmierer hilfreich ist. Kommentare werden in der Regel verwendet, um Code zu Referenzzwecken mit Anmerkungen zu versehen. Der Compiler behandelt sie als Leerzeichen. Sie können Kommentare beim Testen verwenden, um bestimmte Codezeilen als inaktiv zu markieren; allerdings `#if` / `#endif` -präprozessoranweisungen besser dafür da können Sie Code, der Kommentare enthält umgeben, aber Kommentare nicht schachteln.

Es gibt folgende Möglichkeiten, einen C++-Kommentar zu schreiben:

- Die Zeichen `/*` (Schrägstrich, Sternchen), gefolgt von einer beliebigen Folge von Zeichen (einschließlich neuer Zeilen), gefolgt von den Zeichen `*/`. Diese Syntax ist mit der Syntax von ANSI C identisch.

- Die Zeichen `//` (zwei Schrägstriche), gefolgt von einer beliebigen Folge von Zeichen. Eine neue Zeile, der nicht direkt ein umgekehrter Schrägstrich vorangestellt ist, beendet diese Art des Kommentars. Daher wird dies häufig als "einzeiliger Kommentar" bezeichnet.

Die Kommentarzeichen (`/*`, `*/` und `//`) verfügen über keine besondere Bedeutung innerhalb einer Zeichenkonstante, eines Zeichenfolgenliterals oder eines Kommentars. Kommentare, die die erste Syntax verwenden, können deshalb nicht geschachtelt werden.

## <a name="see-also"></a>Siehe auch

[Lexikalische Konventionen](../cpp/lexical-conventions.md)