---
title: 'Vorgehensweise: Debuggen eines Releasebuilds | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds, debugging
ms.assetid: d333e4d1-4e6c-4384-84a9-cb549702da25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31113d9a5935536ac10b22c7b5f5af27b0d29970
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-debug-a-release-build"></a>Gewusst wie: Debuggen eines Releasebuilds
Sie können einen Releasebuild der Anwendung debuggen.  
  
### <a name="to-debug-a-release-build"></a>So debuggen Sie einen Releasebuild  
  
1.  Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **C/C++-** Knoten. Legen Sie **Debuginformationsformat** auf [C7-kompatibel (/ Z7)](../../build/reference/z7-zi-zi-debug-information-format.md) oder **Programmdatenbank (/ Zi)**.  
  
3.  Erweitern Sie **Linker** , und klicken Sie auf die **allgemeine** Knoten. Legen Sie **inkrementelles Verknüpfen aktivieren** auf [Nein (/ INCREMENTAL: NO)](../../build/reference/incremental-link-incrementally.md).  
  
4.  Wählen Sie die **Debuggen** Knoten. Legen Sie **Debuginfo generieren** auf [Ja (/ DEBUG)](../../build/reference/debug-generate-debug-info.md).  
  
5.  Wählen Sie die **Optimierung** Knoten. Legen Sie **Verweise** auf [/OPT: REF](../../build/reference/opt-optimizations.md) und **COMDAT-Faltung aktivieren** auf [/OPT: ICF](../../build/reference/opt-optimizations.md).  
  
6.  Sie können nun das Releasebuild der Anwendung debuggen. Um ein Problem, durchlaufen Sie den Code (oder verwenden Sie Just-in-Time-Debuggen) feststellen, bis Sie feststellen, wo der Fehler auftritt, und ermitteln Sie dann die falsche Parameter oder den Code.  
  
     Wenn eine Anwendung in einem Debugbuild funktioniert jedoch in einem Releasebuild fehlschlägt, kann eine vom compileroptimierungen einen Fehler im Quellcode verfügbar gemacht werden werden. Um das Problem zu isolieren, deaktivieren Sie ausgewählte Optimierungen für jede Quellcodedatei, bis Sie die Datei und die Optimierung die Ursache des Problems gefunden. (Um den Prozess zu beschleunigen, können Sie die Dateien in zwei Gruppen unterteilt, deaktivieren Optimierung für eine Gruppe, und wenn Sie in einer Gruppe auf ein Problem stoßen weiterhin geteilt, bis Sie die Problemdatei eingegrenzt haben.)  
  
     Sie können [/RTC](../../build/reference/rtc-run-time-error-checks.md) um solche Fehler in Debugbuilds offen zu legen.  
  
     Weitere Informationen finden Sie unter [des Codes optimieren](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)