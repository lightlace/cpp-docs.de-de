---
title: Schwerwiegender Fehler C1305 | Microsoft Docs
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
ms.openlocfilehash: 3cb1cf19d0fc4152fbb458d684972bb5a4418f37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1305"></a>Schwerwiegender Fehler C1305
Die Profildatenbank 'PDG-Datei' wird für eine andere Architektur verwendet.  
  
 PGD-Datei, die von der/LTCG: PGINSTRUMENT-Operation generiert wurde, für eine andere Plattform übergeben wurde [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md) stehen für X86 und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Plattformen. Eine mit einer /LTCG:PGINSTRUMENT-Operation für eine bestimmte Plattform erzeugte PGD-Datei ist jedoch ungültig als Eingabe für eine /LTCG:PGOPTIMIZE-Operation für eine andere Plattform.  
  
 Um diesen Fehler zu beheben, geben Sie eine mit /LTCG:PGINSTRUMENT erstellte PGD-Datei nur an /LTCG:PGOPTIMIZE für dieselbe Plattform weiter.