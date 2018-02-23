---
title: "Kompatibilität | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bed3ebc3723bfe6af8e3d12fc3702ecb0dda7b4f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="compatibility"></a>Kompatibilität
Die universelle C-Laufzeitbibliothek (UCRT, Universal C Run-Time Library) unterstützt den größten Teil der C-Standardbibliothek, der für die C++-Kompatibilität erforderlich ist. Sie implementiert die C99-Bibliothek (ISO/IEC 9899:1999), mit Ausnahme der in \<tgmath.h> definierten typgenerischen Makros und der strengen Typkompatibilität in \<complex.h>. Die UCRT implementiert darüber hinaus eine große Teilmenge der POSIX.1-C-Bibliothek (ISO/IEC 9945-1:1996, die POSIX-System-Anwendungsprogrammierschnittstelle), ist aber nicht vollständig mit einem spezifischen POSIX-Standard konform.  Außerdem implementiert die UCRT eine Reihe von Microsoft-spezifischen Funktionen und Makros, die nicht Bestandteil eines Standards sind.  
  
 Die für die Microsoft-Implementierung von Visual C++ spezifischen Funktionen befinden sich in der vcruntime-Bibliothek.  Viele dieser Funktionen dienen der internen Verwendung und können nicht von Benutzercode aufgerufen werden. Einige sind für den Gebrauch beim Debuggen und aus Gründen der Implementierungskompatibilität dokumentiert.  
  
 Im C++-Standard sind Namen, die im globalen Namespace mit einem Unterstrich beginnen, für die Implementierung reserviert. Da sich die POSIX-Funktionen im globalen Namespace befinden, aber nicht Teil der Standard-C-Laufzeitbibliothek sind, weisen die Microsoft-spezifischen Implementierungen dieser Funktionen einen führenden Unterstrich auf. Aus Gründen der Portierbarkeit unterstützt die UCRT außerdem die Standardnamen. Der Visual C++-Compiler gibt jedoch beim Kompilieren von Code eine Veraltungswarnung aus, wenn dieser Standardnamen verwendet. Nur die POSIX-Standardnamen sind veraltet, nicht die Funktionen. Um die Warnung zu unterdrücken, definieren Sie `_CRT_NONSTDC_NO_WARNINGS` , bevor Sie Header in den Code einschließen, in denen die ursprünglichen POSIX-Namen verwendet werden.  
  
 Bestimmte Funktionen in der Standard-C-Bibliothek wurden in der Vergangenheit aufgrund missbräuchlich verwendeter Parameter und nicht deaktivierter Puffer häufig unsicher verwendet. Diese Funktionen stellen oft die Ursache von Sicherheitsproblemen im Code dar. Microsoft hat eine Sammlung sichererer Versionen dieser Funktionen erstellt, die die Verwendung der Parameter überprüfen und den Handler für ungültige Parameter aufrufen, wenn hier zur Laufzeit ein Problem erkannt wird.  Standardmäßig gibt der Visual C++-Compiler eine Veraltungswarnung aus, wenn eine Funktion verwendet wird, zu der eine sicherere Variante verfügbar ist. Wenn Sie Ihren Code als C++ kompilieren, können Sie `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` auf 1 festlegen, um die meisten Warnungen zu beseitigen. Dabei werden Vorlagenüberladungen verwendet, um die sichereren Varianten aufzurufen, zugleich aber den portierbaren Quelltext beizubehalten. Um die Warnung zu unterdrücken, definieren Sie `_CRT_SECURE_NO_WARNINGS` , bevor Sie Header in den Code einschließen, die diese Funktionen verwenden. Weitere Informationen finden Sie unter [Security Features in the CRT](../c-runtime-library/security-features-in-the-crt.md).  
  
 Sofern nicht in der Dokumentation zu bestimmten Funktionen anders vermerkt, ist die UCRT mit der Windows-API kompatibel.  Bestimmte Funktionen werden in Apps für den Windows 8 Store oder in universellen Windows Plattform-Apps (UWP) unter Windows 10 nicht unterstützt. Diese Funktionen sind unter [CRT-Funktionen, die nicht von UWP-Apps unterstützt werden](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) aufgelistet, dort sind die von der Windows-Runtime und [UWP](/uwp) nicht unterstützten Funktionen aufgezählt.  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|Titel|description|  
|-----------|-----------------|  
|[UWP-Apps, die Windows-Runtime und die C-Runtime](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Beschreibt, wann UCRT-Routinen nicht mit universellen Windows-Apps oder Microsoft Store-Apps kompatibel sind.|  
|[ANSI C-Kompatibilität](../c-runtime-library/ansi-c-compliance.md)|Beschreibt die normgerechte Benennung in der UCRT.|  
|[UNIX](../c-runtime-library/unix.md)|Enthält Richtlinien zum Portieren von Programmen zu UNIX.|  
|[Windows-Plattformen (CRT)](../c-runtime-library/windows-platforms-crt.md)|Listet die Betriebssysteme auf, die durch CRT unterstützt werden.|  
|[Abwärtskompatibilität](../c-runtime-library/backward-compatibility.md)|Beschreibt, wie alte CRT-Namen neuen zugeordnet werden.|  
|[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)|Bietet eine Übersicht über die CRT-Bibliotheksdateien (.lib) und über die zugehörigen Compileroptionen.|