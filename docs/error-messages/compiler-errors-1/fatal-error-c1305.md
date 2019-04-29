---
title: Schwerwiegender Fehler C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 988842a0d5e8002ffd1478a2e10a8c88ee971911
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397496"
---
# <a name="fatal-error-c1305"></a>Schwerwiegender Fehler C1305

Die Profildatenbank 'PDG-Datei' wird für eine andere Architektur verwendet.

PGD-Datei, die aus der/LTCG: PGINSTRUMENT-Operation generiert wurde, für eine andere Plattform übergeben wurde [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profilgesteuerte Optimierungen](../../build/profile-guided-optimizations.md) für X86- und X64 Plattformen verfügbar sind. Eine mit einer /LTCG:PGINSTRUMENT-Operation für eine bestimmte Plattform erzeugte PGD-Datei ist jedoch ungültig als Eingabe für eine /LTCG:PGOPTIMIZE-Operation für eine andere Plattform.

Um diesen Fehler zu beheben, geben Sie eine mit /LTCG:PGINSTRUMENT erstellte PGD-Datei nur an /LTCG:PGOPTIMIZE für dieselbe Plattform weiter.