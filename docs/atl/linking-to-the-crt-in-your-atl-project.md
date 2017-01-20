---
title: "Linking to the CRT in Your ATL Project"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DllMainCRTStartup"
  - "wWinMainCRTStartup"
  - "WinMainCRTStartup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, C Run-Time library (CRT)"
  - "CRT, linking with ATL"
  - "DllMainCRTStartup method"
  - "WinMainCRTStartup method"
  - "wWinMainCRTStartup method"
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Linking to the CRT in Your ATL Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md) \(CRT\) bieten zahlreiche nützliche Funktionen, die Programmierung viel einfacher machen können während ATL\-Entwicklung.  Alle ATL\-Projekt\-Link zur CRT\-Bibliothek.  Sie können die Vor\- und Nachteile der Verknüpfung von Methode in [Vorteile und Kompromisse der Methode verwendet, um mit CRT verknüpft](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md) finden.  
  
## Auswirkungen der Verknüpfung mit CRT auf dem Programmimage  
 Wenn Sie statisch mit CRT verknüpfen, wird Code von CRT in das ausführbares Bild platziert und Sie, müssen nicht die CRT\-DLL verfügen, das auf einem System vorhanden ist, um das Bilder auszuführen.  Wenn Sie dynamisch mit CRT verknüpfen, werden Verweise auf Code in CRT\-DLL im Bild, jedoch nicht im Code selbst eingefügt.  Damit das Bild zur Ausführung auf einem angegebenen System, muss die CRT\-DLL auf diesem System vorhanden sein.  Auch wenn Sie dynamisch mit CRT verknüpfen, stellen Sie möglicherweise fest, dass jeder Code \(beispielsweise, **DllMainCRTStartup**\) statisch verknüpft werden können.  
  
 Wenn Sie das Bild verknüpfen, geben Sie entweder explizit oder implizit einen Einstiegspunkt an, den das Betriebssystem in aufruft, nachdem es das Bild geladen wurde.  Für eine DLL ist der Standardwert **DllMainCRTStartup** Einstiegspunkt.  Für eine EXE\-Datei ist es **WinMainCRTStartup**.  Sie können die Standardeinstellung mit der \/ENTRY\- Linkeroption überschreiben.  Die CRT stellt eine Implementierung für **DllMainCRTStartup**, **WinMainCRTStartup** und **wWinMainCRTStartup** \(Unicode\-Einstiegspunkt für eine EXE\-Datei\) bereit.  Diese CRT\-stellten Einstiegspunktaufrufskonstruktoren auf globalen Objekten bereit und initialisieren andere Datenstrukturen, die von mehreren CRT\-Funktionen verwendet werden.  Dieser Startcode fügt über 25K Bild hinzu, wenn er statisch verknüpft ist.  Wenn er dynamisch verknüpft ist, befindet sich der Code in der DLL, daher bleibt die Bildgröße klein.  
  
 Weitere Informationen finden Sie im Linkerthema [\/ENTRY \(Einstiegspunkt\-Symbol\)](../build/reference/entry-entry-point-symbol.md).  
  
## Optimierungs\-Optionen  
 Verwenden der Linkeroption \/OPT:NOWIN98 kann ein Steuerelement mit ATL von 10K, auf Kosten von erhöhter Ladezeit auf Windows 98\-Systemen weiter verringern.  Weitere Informationen zum Verknüpfen von Optionen, finden Sie unter [\/OPT \(Optimierungen\)](../build/reference/opt-optimizations.md).  
  
## Siehe auch  
 [Programmieren mit ATL\- und C\-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Verhalten der Laufzeitbibliothek](../build/run-time-library-behavior.md)