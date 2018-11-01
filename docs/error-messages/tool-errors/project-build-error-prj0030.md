---
title: Projektbuildfehler PRJ0030
ms.date: 11/04/2016
f1_keywords:
- PRJ0030
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
ms.openlocfilehash: 2a6cde4ca48acb9aadfe3109084483dbb554e1e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488074"
---
# <a name="project-build-error-prj0030"></a>Projektbuildfehler PRJ0030

Makrofehler-Erweiterung. Werten Sie Überprüfungsrekursion überschritt 32 Ebenen für $(Makro) ein.

Dieser Fehler wird durch die Rekursion in Makros verursacht. Wenn Sie festlegen, z. B. die **Zwischenverzeichnis** Eigenschaft (finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md)) auf $(intdir), werden Sie Rekursion haben.

Um diesen Fehler zu beheben, ist nicht definiert, Makros oder Eigenschaften in Bezug auf die Makros, die sie verwendet werden, um zu definieren.