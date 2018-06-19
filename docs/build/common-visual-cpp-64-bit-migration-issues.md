---
title: Häufig auftretende von Visual C++-64-Bit-Migrationsprobleme bei | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- upgrading Visual C++ applications, 32-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab4b8a8e693a9e1a87ddb3a06fe609416808d3dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367728"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Häufig auftretende 64-Bit-Migrationsprobleme bei Visual C++

Wenn Sie mit Visual C++ Anwendungen erstellen, die unter einem 64-Bit-Windows-Betriebssystem ausgeführt werden sollen, sollten Sie folgende Probleme berücksichtigen:  
  
-   `int` und `long` sind unter 64-Bit-Windows-Betriebssystemen 32-Bit-Werte. Bei Programmen, die Sie für 64-Bit-Plattformen kompilieren möchten, sollten Sie darauf achten, keine Zeiger auf 32-Bit-Variablen zuzuweisen. Zeiger sind auf 64-Bit-Plattformen 64-Bit-Werte, und der Zeigerwert wird abgeschnitten, wenn Sie sie einer 32-Bit-Variable zuweisen.  
  
-   `size_t`, `time_t`, und `ptrdiff_t` sind unter 64-Bit-Windows-Betriebssystemen 64-Bit-Werte.  
  
-   `time_t` ist unter 32-Bit-Windows-Betriebssystemen in Visual C++-Versionen vor Visual C++ 2005 ein 32-Bit-Wert. `time_t` ist jetzt standardmäßig eine 64-Bit-Ganzzahl. Weitere Informationen finden Sie unter [Uhrzeitverwaltung](../c-runtime-library/time-management.md).  
  
     Sie müssen berücksichtigen, wo der Code einen `int`-Wert nimmt und als einen `size_t`- oder `time_t`-Wert verarbeitet. Die Zahl kann unter Umständen größer als eine 32-Bit-Zahl werden, und Daten werden abgeschnitten, wenn sie wieder an den `int`-Speicher übergeben werden.  
  
Der %x-Modifzierer(Hexadezimal-`int`-Format) `printf` funktioniert unter einem 64-Bit-Windows-Betriebssystem nicht wie erwartet. Er funktioniert nur auf den ersten 32 Bits des Werts, der an ihn übergeben wird.  
  
-   Verwenden Sie %I32x, um einen 32-Bit-Ganzzahltyp im Hexadezimalformat anzuzeigen.  
  
-   Verwenden Sie %I64x, um einen 64-Bit-Ganzzahltyp im Hexadezimalformat anzuzeigen.  
  
-   %p (Hexadezimalformat für einen Zeiger) funktioniert unter einem 64-Bit-Windows-Betriebssystem wie erwartet.  
  
Weitere Informationen finden Sie unter:  
  
-   [Compileroptionen](../build/reference/compiler-options.md)  
  
-   [Tipps zur Migration](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## <a name="see-also"></a>Siehe auch  

[Konfigurieren von Visual C++ für die 64-Bit-X64 Ziele](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[Visual C++-Handbuch: Portieren und Aktualisieren](../porting/visual-cpp-porting-and-upgrading-guide.md)