---
title: Schwerwiegender Fehler C1305 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4beb1140d161b8cbe54cab40dcc72899c976edc3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048746"
---
# <a name="fatal-error-c1305"></a>Schwerwiegender Fehler C1305

Die Profildatenbank 'PDG-Datei' wird für eine andere Architektur verwendet.

PGD-Datei, die aus der/LTCG: PGINSTRUMENT-Operation generiert wurde, für eine andere Plattform übergeben wurde [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md) für X86- und X64 Plattformen verfügbar sind. Eine mit einer /LTCG:PGINSTRUMENT-Operation für eine bestimmte Plattform erzeugte PGD-Datei ist jedoch ungültig als Eingabe für eine /LTCG:PGOPTIMIZE-Operation für eine andere Plattform.

Um diesen Fehler zu beheben, geben Sie eine mit /LTCG:PGINSTRUMENT erstellte PGD-Datei nur an /LTCG:PGOPTIMIZE für dieselbe Plattform weiter.