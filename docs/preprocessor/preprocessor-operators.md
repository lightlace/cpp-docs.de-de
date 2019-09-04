---
title: Präprozessoroperatoren
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor operators
- operators [C++], preprocessor
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
ms.openlocfilehash: 1c556e4af5913ba8d0dc7efc9648e0d0004d9d7e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222253"
---
# <a name="preprocessor-operators"></a>Präprozessoroperatoren

Vier präprozessorspezifische Operatoren werden im Kontext der `#define` -Direktive verwendet. In der folgenden Tabelle finden Sie eine Zusammenfassung der einzelnen-Informationen. Zeichenfolgenoperatoren, Zeichenoperatoren und Operatoren zum Einfügen eines Tokens werden in den nächsten drei Abschnitten erläutert. Weitere Informationen zum- `defined` Operator finden Sie in [den Anweisungen #if, #elif, #else und #endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

|Operator|Aktion|
|--------------|------------|
|[Zeichen folgen Operator (#)](../preprocessor/stringizing-operator-hash.md)|Bewirkt, dass das entsprechende tatsächliche Argument in doppelte Anführungszeichen eingeschlossen wird.|
|[Der Operator (# @)](../preprocessor/charizing-operator-hash-at.md)|Bewirkt, dass das entsprechende Argument in einfache Anführungszeichen eingeschlossen und als Zeichen behandelt wird (Microsoft-spezifisch).|
|[Tokeneinfügender Operator (# #)](../preprocessor/token-pasting-operator-hash-hash.md)|Ermöglicht das Verketten der Token, die als tatsächliche Argumente verwendet werden, um andere Token zu bilden.|
|[definierter Operator](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Vereinfacht das Schreiben von zusammengesetzten Ausdrücken in bestimmten Makroanweisungen.|

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)\
[Vordefinierte Makros](../preprocessor/predefined-macros.md)\
[c/c++-präprozessorverweis](../preprocessor/c-cpp-preprocessor-reference.md)
