---
title: Projektbuildfehler PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: aa1c8539247287f7644742857c3cb7de321a20a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385393"
---
# <a name="project-build-error-prj0030"></a>Projektbuildfehler PRJ0030

Makrofehler-Erweiterung. Werten Sie Überprüfungsrekursion überschritt 32 Ebenen für $(Makro) ein.

Dieser Fehler wird durch die Rekursion in Makros verursacht. Wenn Sie festlegen, z. B. die **Zwischenverzeichnis** Eigenschaft (finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../build/reference/general-property-page-project.md)) auf $(intdir), werden Sie Rekursion haben.

Um diesen Fehler zu beheben, ist nicht definiert, Makros oder Eigenschaften in Bezug auf die Makros, die sie verwendet werden, um zu definieren.