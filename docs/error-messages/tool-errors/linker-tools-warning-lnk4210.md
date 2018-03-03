---
title: Linkertoolwarnung Lnk4210 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4e2d596527b60735b42fb4edfff6f36d0be808d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4210"></a>Linkertoolwarnung LNK4210  
  
> Abschnitt *Abschnitt* vorhanden ist; es kann nicht behandelt würden statische Initialisierer oder Abschlusszeichen  
  
Code wurde eingeführt, statische Initialisierer oder Abschlusszeichen, aber der Startcode der VCRuntime-Bibliothek oder dessen Entsprechung (die muss zum Ausführen der statischen Initialisierer oder ein Abschlusszeichen) wird nicht ausgeführt, beim Starten der Anwendung. Hier sind einige Beispiele für Code, der statische Initialisierer oder Abschlusszeichen erfordert:  
  
-   Globale Class-Variable mit einem Konstruktor, Destruktor oder virtuelle Funktionstabelle.  
  
-   Globale Variable mit einem nicht-Kompilierzeitkonstante initialisiert.  
  
Um dieses Problem zu beheben, führen Sie eine der folgenden aus:  
  
-   Entfernen Sie sämtlichen Code mit statischen Initialisierern.  
  
-   Verwenden Sie keine [/NOENTRY](../../build/reference/noentry-no-entry-point.md). Nach dem Entfernen von/NOENTRY müssen Sie auch entfernen [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) der Linker-Befehlszeile.  
  
-   Wenn Ihr Build/MT verwendet, fügen Sie "LIBCMT.lib" libvcruntime.lib und "libucrt.lib" in der Linker-Befehlszeile ein. Wenn Ihr Build/MTd verwendet, fügen Sie libcmtd.lib, vcruntimed.lib und libucrtd.lib.  
  
-   Beim Verschieben von/CLR: pure-Kompilierung zu/CLR, entfernen Sie die [/Entry](../../build/reference/entry-entry-point-symbol.md) Option in der Linker-Befehlszeile. Dies ermöglicht CRT-Initialisierung und statische Initialisierer beim Anwendungsstart ausgeführt werden.  
  
 Die [/GS](../../build/reference/gs-buffer-security-check.md) -Compileroption erfordert Initialisierung durch die `__security_init_cookie` Funktion. Diese Initialisierung wird bereitgestellt, in der Startcode VCRuntime-Bibliothek, die ausgeführt, in wird der Standardeinstellung `_DllMainCRTStartup`.  
  
-   Wenn Ihr Projekt erstellt wurde, verwenden / Entry und/Entry anders als eine Funktion übergeben wird `_DllMainCRTStartup`, rufen Sie die Funktion muss `_CRT_INIT` CRT initialisiert werden. Dieser Aufruf allein ist nicht ausreichend, wenn die DLL/GS verwendet, statische Initialisierer erfordert oder im Kontext der MFC oder ATL-Code aufgerufen wird. Finden Sie unter [DLLs und Visual C++-Laufzeitbibliothek Verhalten](../../build/run-time-library-behavior.md) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)