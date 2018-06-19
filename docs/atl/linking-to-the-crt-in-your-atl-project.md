---
title: Verknüpfen mit der CRT in ATL-Projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- DllMainCRTStartup
- wWinMainCRTStartup
- WinMainCRTStartup
dev_langs:
- C++
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0d93f8770ebbd893491c0e8b8eed239396e00a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356382"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>Verknüpfen mit der CRT in ATL-Projekt
Die [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md) (CRT) bieten zahlreiche nützliche Funktionen, die während der Entwicklung von ATL-Programmierung wesentlich einfacher vornehmen können. Alle ATL-Projekte, die mit der CRT-Bibliothek verknüpft werden. Sehen Sie die vor- und Nachteile der Methode in verknüpfen [vor- und Nachteile von der Methode verwendet, um die Verknüpfung mit der CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>Auswirkungen der Verknüpfung mit der CRT auf das Programmabbild  
 Wenn Sie mit der CRT statisch verknüpft, wird Code aus der CRT in Ihre ausführbaren Image eingefügt und müssen nicht die CRT-DLL vorhanden auf einem System, das Abbild ausgeführt haben. Wenn Sie dynamisch mit der CRT verknüpft, werden Verweise auf den Code in der CRT-DLL in Ihrem Image, nicht jedoch der Code selbst platziert. In der Reihenfolge für das Abbild auf einem bestimmten System ausführen muss die CRT-DLL auf diesem System vorhanden sein. Auch wenn Sie dynamisch mit der CRT verknüpfen, können möglicherweise einige Code statisch verknüpft werden kann (z. B. **DllMainCRTStartup**).  
  
 Wenn Sie das Abbild verknüpfen, geben Sie entweder explizit oder implizit einen Einstiegspunkt, den das Betriebssystem nach dem Laden des Bilds in aufruft. Für eine DLL ist der Standardeinstiegspunkt **DllMainCRTStartup**. Bei einer EXE-Datei lautet **WinMainCRTStartup**. Sie können die Standardeinstellung für die/Entry (Linkeroption) überschreiben. Die CRT stellt eine Implementierung für **DllMainCRTStartup**, **WinMainCRTStartup**, und **wWinMainCRTStartup** (Unicode-Einstiegspunkt für eine EXE-Datei). Diese Einstiegspunkte CRT bereitgestellten Konstruktoren für globale Objekte aufrufen und initialisieren Sie andere Datenstrukturen, die von einigen CRT-Funktionen verwendet werden. Dieser Startcode hinzugefügt Ihres Images ca. 25 KB, wenn sie statisch verknüpft ist. Dynamisch verknüpft, Großteil des Codes wird in der DLL, damit die Größe Ihres Images klein bleibt.  
  
 Weitere Informationen finden Sie im Linkerthema [/Entry (Symbol für Einstiegspunkt)](../build/reference/entry-entry-point-symbol.md).  
  
## <a name="optimization-options"></a>Optimierungsoptionen  
 Die Linkeroption/OPT: NOWIN98 kann weiter ein standardmäßiges ATL-Steuerelement von 10 KB auf Kosten der reduzieren Ladezeiten bei Windows 98-Systeme. Weitere Informationen zum Verknüpfen von Optionen finden Sie unter [/OPT (Optimierungen)](../build/reference/opt-optimizations.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Programmieren mit ATL- und C-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../build/run-time-library-behavior.md)

