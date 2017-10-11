---
title: Schwerwiegender Fehler C1305 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cf4a9025b8d441ae42b7de7605594fda60dc5603
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1305"></a>Schwerwiegender Fehler C1305
Die Profildatenbank 'PDG-Datei' wird für eine andere Architektur verwendet.  
  
 PGD-Datei, die von der/LTCG: PGINSTRUMENT-Operation generiert wurde, für eine andere Plattform übergeben wurde [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md) stehen für X86 und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] Plattformen. Eine mit einer /LTCG:PGINSTRUMENT-Operation für eine bestimmte Plattform erzeugte PGD-Datei ist jedoch ungültig als Eingabe für eine /LTCG:PGOPTIMIZE-Operation für eine andere Plattform.  
  
 Um diesen Fehler zu beheben, geben Sie eine mit /LTCG:PGINSTRUMENT erstellte PGD-Datei nur an /LTCG:PGOPTIMIZE für dieselbe Plattform weiter.
