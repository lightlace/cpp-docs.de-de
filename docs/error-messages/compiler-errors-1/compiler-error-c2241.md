---
title: Compilerfehler C2241
ms.date: 11/04/2016
f1_keywords:
- C2241
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
ms.openlocfilehash: 88f25931d84fe3884ebecbc97b9ddd73390bacc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388968"
---
# <a name="compiler-error-c2241"></a>Compilerfehler C2241

'Bezeichner': Memberzugriff ist eingeschränkt.

Der Code versucht, auf einen privaten oder geschützten Member zuzugreifen.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Ändern Sie die Zugriffsebene des Members.

1. Deklarieren Sie den Member als `friend` der zugreifenden Funktion.