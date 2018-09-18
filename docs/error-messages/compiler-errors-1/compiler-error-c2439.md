---
title: Compilerfehler C2439 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 419bf7be45a1383135d0231cd059837e1fe62729
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058411"
---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439

'Bezeichner': Member konnte nicht initialisiert werden

Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Versuch, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.

1. Versuch, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Durch den Konstruktor der Klasse oder Struktur muss ein geerbter Member initialisiert werden.