---
title: Compilerfehler C2439
ms.date: 11/04/2016
f1_keywords:
- C2439
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
ms.openlocfilehash: f71112d3f37f3e4d1a4f41bade95726d7aa0a0bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311732"
---
# <a name="compiler-error-c2439"></a>Compilerfehler C2439

'Bezeichner': Member konnte nicht initialisiert werden

Eine Klasse, Struktur oder union-Member kann nicht initialisiert werden.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Versuch, eine indirekte Basisklasse der Klasse oder Struktur zu initialisieren.

1. Versuch, einen geerbten Member einer Klasse oder Struktur zu initialisieren. Durch den Konstruktor der Klasse oder Struktur muss ein geerbter Member initialisiert werden.