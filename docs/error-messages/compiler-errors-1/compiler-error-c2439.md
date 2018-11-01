---
title: Compilerfehler C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: f71112d3f37f3e4d1a4f41bade95726d7aa0a0bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644356"
---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439

'Bezeichner': Member konnte nicht initialisiert werden

Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Versuch, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.

1. Versuch, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Durch den Konstruktor der Klasse oder Struktur muss ein geerbter Member initialisiert werden.