---
title: -Q-Optionen (Operationen auf niedriger Ebene) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /q
dev_langs: C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d970c2de5e34840ab2ed77f229c329db3c6f72fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="q-options-low-level-operations"></a>/Q-Optionen (Operationen auf niedriger Ebene)
Sie können die **/q /** -Compileroptionen zur Durchführung der folgenden Compilervorgänge:  
  
-   [/ Qfast_transcendentals (Erzwingen von schnellen transzendenten)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): generiert schnelle Transzendente.  
  
-   [/ QIfist (_ftol unterdrücken)](../../build/reference/qifist-suppress-ftol.md): unterdrückt `_ftol` Wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich (nur X86) ist.  
  
-   [/ Qimprecise_fwaits (Entfernen von Fwaits in Try-Blöcken)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): entfernt `fwait` -Befehle in `try` blockiert.  
  
-   [/ Qpar (automatische Parallelisierung)](../../build/reference/qpar-auto-parallelizer.md): ermöglicht automatische Parallelisierung von Schleifen, die mit markiert sind die [#pragma loop()](../../preprocessor/loop.md) Richtlinie.  
  
-   [/ Qpar-Report (Auto-Parallelisierer Reporting Stufe)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Parallelisierung.  
  
-   [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): unterdrückt Optimierungen für Gleitkommaregister lädt und für wechselt zwischen Arbeitsspeicher und MMX registriert.  
  
-   [/ Qvec-Report (Auto-Vektorisierer Reporting Stufe)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): aktiviert die Berichterstellungsebenen für die automatische Vektorisierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)