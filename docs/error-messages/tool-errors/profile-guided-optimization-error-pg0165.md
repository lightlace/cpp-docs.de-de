---
title: 'Fehler in profilgesteuerter Optimierung: PG0165'
ms.date: 11/04/2016
f1_keywords:
- PG0165
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
ms.openlocfilehash: f39bbe6540ebec10cd25c41ac2fe9f2acfca9b13
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359734"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler in profilgesteuerter Optimierung: PG0165

Lesen Sie 'Dateiname.PGD': ' PGD-Version wird nicht unterstützt werden (Versionskonflikt) ".

PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als die zum Verwenden *Filename*PGD. Dieser Fehler weist darauf hin, dass Compilertoolset nicht verwenden kann, die Daten aus *Filename*PGD, um die aktuelle Anwendung zu optimieren.

Um dieses Problem zu beheben, neu generieren *Filename*PGD mit dem aktuellen Compilertoolset.