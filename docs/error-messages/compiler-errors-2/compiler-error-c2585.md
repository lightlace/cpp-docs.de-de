---
title: Compilerfehler C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 812ab15aacd1f6a215c6a5beb7781983859fe858
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593257"
---
# <a name="compiler-error-c2585"></a>Compilerfehler C2585

die explizite Konvertierung in 'type' ist mehrdeutig

Die typkonvertierung kann mehr als ein Ergebnis erzeugen.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Konvertieren von einem Typ Klasse oder Struktur, die basierend auf mehrfache Vererbung. Wenn der Typ mehr als einmal derselben Basisklasse erbt, die Konvertierungsfunktion or -Operator muss verwenden bereichsauflösung (`::`) angeben, welche von der geerbten Klassen, die bei der Konvertierung verwendet.

1. Ein Konvertierungsoperator und einen Konstruktor haben die gleiche Konvertierung vornehmen definiert wurde.