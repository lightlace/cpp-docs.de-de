---
title: UNIX | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 500280e2818908930fe2e3fe2608e217e1ba4b49
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="unix"></a>UNIX
Wenn Sie Ihre Programme nach UNIX portieren möchten, befolgen Sie folgende Richtlinien:  
  
-   Entfernen Sie keine Headerdateien aus dem SYS-Unterverzeichnis. Sie können die SYS-Headerdateien nur an eine andere Stelle verschieben, wenn Sie nicht beabsichtigen, Ihre Programme nach UNIX zu portieren.  
  
-   Verwenden Sie die UNIX-kompatiblen Pfadtrennzeichen in Routinen, die Zeichenfolgen für Pfade und Dateinamen als Argumente annehmen. UNIX unterstützt für diesen Zweck nur Schrägstriche (/), wohingegen Win32-Betriebssysteme sowohl umgekehrte Schrägstriche (\\) als auch Schrägstriche (/) unterstützen. Deshalb werden in dieser Dokumentation beispielsweise UNIX-kompatible Schrägstriche als Pfadtrennzeichen in `#include`-Anweisungen verwendet. (Allerdings unterstützt die Befehlsshell des Windows-Betriebssystems, CMD.EXE, keine Schrägstriche in Befehlen, die in der Eingabeaufforderung eingegeben werden.)  
  
-   Verwenden Sie ordnungsgemäß funktionierende Pfade und Dateinamen in UNIX, in der die Groß-/Kleinschreibung gilt. Beim FAT-Dateisystem (File Allocation Table) in Win32-Betriebssystemen muss die Groß-/Kleinschreibung nicht berücksichtigt werden. Das NTFS-Dateisystem behält zwar Groß-/Kleinschreibung für Verzeichnislisten bei, ignoriert jedoch die Groß-/Kleinschreibung bei Dateisuchen und anderen Systemvorgängen.  
  
    > [!NOTE]
    >  In dieser Version von Visual C++ wurden UNIX-Kompatibilitätsinformationen aus den Beschreibungen der Funktionen entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)
