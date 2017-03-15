---
title: "Linkertoolwarnung LNK4210 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4210"
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Linkertoolwarnung LNK4210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Abschnitt'\-Abschnitt vorhanden; es sind möglicherweise unbehandelte statische Initialisierer oder Terminatoren vorhanden  
  
 Im Code wurden statische Initialisierungen oder Terminatoren implementiert, der CRT oder ein entsprechendes Element \(das die statischen Initialisierungen oder Terminatoren ausführen muss\) wird jedoch beim Anwendungsstart nicht ausgeführt.  Codebeispiele, die dieses Szenario verursachen, umfassen:  
  
-   Globale Klassenvariablen mit einem Konstruktor, Destruktor oder einer virtuellen Funktionstabelle.  
  
-   Globale Variablen, die mit einer von der Kompilierungszeit nicht unterstützten Konstanten initialisiert werden.  
  
 Führen Sie zur Behebung dieses Problems einen der folgenden Schritte aus:  
  
-   Entfernen Sie den gesamten Code mit statischen Initialisierungen.  
  
-   [\/NOENTRY](../../build/reference/noentry-no-entry-point.md) sollte nicht verwendet werden.  Nach dem Entfernen von \/NOENTRY müssen Sie möglicherweise auch msvcrt.lib, libcmt.lib oder libcmtd.lib zur Linkerbefehlszeile hinzufügen.  
  
-   Fügen Sie der Linkerbefehlszeile msvcrt.lib, libcmt.lib oder libcmtd.lib hinzu.  
  
-   Entfernen Sie beim Wechsel von der \/clr:pure\-Kompilierung nach \/clr die [\/ENTRY](../../build/reference/entry-entry-point-symbol.md)\-Option aus der Linkerzeile.  Dadurch wird die CRT\-Initialisierung aktiviert, sodass beim Anwendungsstart statische Initialisierungen ausgeführt werden können.  
  
-   Wenn das Projekt mit [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) erstellt wurde und an \/ENTRY eine andere Funktion als `_DllMainCRTStartup` übergeben wurde, muss die Funktion CRT\_INIT aufrufen.  Siehe [Laufzeitbibliotheks\-Verhalten](../../build/run-time-library-behavior.md) und im Knowledge Base\-Artikel Q94248, [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;94248](http://support.microsoft.com/default.aspx?scid=kb;en-us;94248) weitere Informationen.  
  
 Die [\/GS](../../build/reference/gs-buffer-security-check.md)\-Compileroption erfordert CRT\-Startcode.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)