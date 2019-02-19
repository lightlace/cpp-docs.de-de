---
title: static-Speicherklassenspezifizierer
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: ef85ee4d757cb9579431427fba7b46a0e5ac905f
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148230"
---
# <a name="static-storage-class-specifier"></a>static-Speicherklassenspezifizierer

Eine Variable, die auf interner Ebene mit dem **static**-Speicherklassenspezifizierer deklariert wurde, hat eine globale Lebensdauer, wird jedoch nur innerhalb des Blocks angezeigt, in dem sie deklariert ist. Bei konstanten Zeichenfolgen ist die Verwendung von **static** nützlich, da es den Mehraufwand einer häufigen Initialisierung in häufig aufgerufenen Funktionen verringert.

## <a name="remarks"></a>Anmerkungen

Wenn Sie nicht explizit eine **static**-Variable initialisieren, wird sie standardmäßig mit 0 (null) initialisiert. Innerhalb einer Funktion bewirkt **static**, dass Speicher zugeordnet wird, und dient als Definition. Interne statische Variablen stellen privaten Festspeicher bereit, der nur für eine einzelne Funktion sichtbar ist.

## <a name="see-also"></a>Siehe auch

[C-Speicherklassen](c-storage-classes.md)<br/>
[Speicherklassen (C++)](../cpp/storage-classes-cpp.md)
