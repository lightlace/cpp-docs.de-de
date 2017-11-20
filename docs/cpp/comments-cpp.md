---
title: Kommentare (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 828d02ddd02c7484e142333bdb87453f8fb922e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comments-c"></a>Kommentare (C++)
Ein Kommentar ist Text, den der Compiler ignoriert, der jedoch für Programmierer hilfreich ist. Kommentare werden in der Regel verwendet, um Code zu Referenzzwecken mit Anmerkungen zu versehen. Der Compiler behandelt sie als Leerzeichen. Sie können Kommentare beim Testen verwenden, um bestimmte Codezeilen als inaktiv zu markieren. allerdings `#if` / `#endif` besser geeignet Präprozessordirektiven dafür da können Sie Code, der Kommentare enthält, umschließen, aber Kommentare nicht schachteln.  
  
 Es gibt folgende Möglichkeiten, einen C++-Kommentar zu schreiben:  
  
-   Die Zeichen `/*` (Schrägstrich, Sternchen), gefolgt von einer beliebigen Folge von Zeichen (einschließlich neuer Zeilen), gefolgt von den Zeichen `*/`. Diese Syntax ist mit der Syntax von ANSI C identisch.  
  
-   Die Zeichen `//` (zwei Schrägstriche), gefolgt von einer beliebigen Folge von Zeichen. Eine neue Zeile, der nicht direkt ein umgekehrter Schrägstrich vorangestellt ist, beendet diese Art des Kommentars. Daher wird dies häufig als "einzeiliger Kommentar" bezeichnet.  
  
 Die Kommentarzeichen (`/*`, `*/` und `//`) verfügen über keine besondere Bedeutung innerhalb einer Zeichenkonstante, eines Zeichenfolgenliterals oder eines Kommentars. Kommentare, die die erste Syntax verwenden, können deshalb nicht geschachtelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Lexikalische Konventionen](../cpp/lexical-conventions.md)