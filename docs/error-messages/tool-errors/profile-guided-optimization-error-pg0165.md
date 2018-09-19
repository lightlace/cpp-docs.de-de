---
title: 'Fehler in Optimierung: PG0165 mit profilgesteuerter | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PG0165
dev_langs:
- C++
helpviewer_keywords:
- PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 332751a123bf7d6414c40b79870b5edf27a3d8a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084210"
---
# <a name="profile-guided-optimization-error-pg0165"></a>Fehler in profilgesteuerter Optimierung: PG0165

Lesen 'Dateiname.PGD': ' PGD-Version wird nicht unterstützt werden (Versionskonflikt) ".

PGD-Dateien sind spezifisch für ein bestimmtes Compilertoolset. Dieser Fehler wird generiert, wenn Sie einen anderen Compiler als die zum Verwenden *Filename*PGD. Dieser Fehler weist darauf hin, dass Compilertoolset nicht verwenden kann, die Daten aus *Filename*PGD, um die aktuelle Anwendung zu optimieren.

Um dieses Problem zu beheben, neu generieren *Filename*PGD mit dem aktuellen Compilertoolset.