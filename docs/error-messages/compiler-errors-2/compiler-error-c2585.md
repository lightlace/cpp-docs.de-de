---
title: Compilerfehler C2585 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec7b1e9c1e5e7894740cc80f9c030fa1ee26ec0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028843"
---
# <a name="compiler-error-c2585"></a>Compilerfehler C2585

die explizite Konvertierung in 'type' ist mehrdeutig

Die typkonvertierung kann mehr als ein Ergebnis erzeugen.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Konvertieren von einem Typ Klasse oder Struktur, die basierend auf mehrfache Vererbung. Wenn der Typ mehr als einmal derselben Basisklasse erbt, die Konvertierungsfunktion or -Operator muss verwenden bereichsauflösung (`::`) angeben, welche von der geerbten Klassen, die bei der Konvertierung verwendet.

1. Ein Konvertierungsoperator und einen Konstruktor haben die gleiche Konvertierung vornehmen definiert wurde.