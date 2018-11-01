---
title: 'Fehler in profilgesteuerter Optimierung: PG0165'
ms.date: 11/04/2016
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: f39bbe6540ebec10cd25c41ac2fe9f2acfca9b13
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434517"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler in profilgesteuerter Optimierung: PG0165

Lesen 'Dateiname.PGD': ' PGD-Version wird nicht unterstützt werden (Versionskonflikt) ".

PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als die zum Verwenden *Filename*PGD. Dieser Fehler weist darauf hin, dass Compilertoolset nicht verwenden kann, die Daten aus *Filename*PGD, um die aktuelle Anwendung zu optimieren.

Um dieses Problem zu beheben, neu generieren *Filename*PGD mit dem aktuellen Compilertoolset.