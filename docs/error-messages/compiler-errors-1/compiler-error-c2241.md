---
title: Compilerfehler C2241
ms.date: 11/04/2016
f1_keywords:
- C2241
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
ms.openlocfilehash: 88f25931d84fe3884ebecbc97b9ddd73390bacc2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618876"
---
# <a name="compiler-error-c2241"></a>Compilerfehler C2241

'Bezeichner': Memberzugriff ist eingeschränkt.

Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Ändern Sie die Zugriffsebene des Members.

1. Deklarieren Sie den Member als `friend` der zugreifenden Funktion.