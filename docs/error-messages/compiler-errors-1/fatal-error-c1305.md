---
title: Schwerwiegender Fehler C1305 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b32f9e7555ce905323fd6074d35f1876cd999edd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1305"></a>Schwerwiegender Fehler C1305
Die Profildatenbank 'PDG-Datei' wird für eine andere Architektur verwendet.  
  
 PGD-Datei, die von der/LTCG: PGINSTRUMENT-Operation generiert wurde, für eine andere Plattform übergeben wurde [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md) stehen für X86 und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Plattformen. Eine mit einer /LTCG:PGINSTRUMENT-Operation für eine bestimmte Plattform erzeugte PGD-Datei ist jedoch ungültig als Eingabe für eine /LTCG:PGOPTIMIZE-Operation für eine andere Plattform.  
  
 Um diesen Fehler zu beheben, geben Sie eine mit /LTCG:PGINSTRUMENT erstellte PGD-Datei nur an /LTCG:PGOPTIMIZE für dieselbe Plattform weiter.