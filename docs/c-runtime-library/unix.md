---
title: "UNIX"
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
  - "unix"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "POSIX-Kompatibilität"
  - "POSIX-Dateinamen"
  - "UNIX"
  - "UNIX, Kompatibilität"
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# UNIX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie beabsichtigen, die Programme dem UNIX\- zu portieren, befolgen Sie diese Richtlinien:  
  
-   Entfernen Sie Headerdateien nicht vom SYS\-Unterverzeichnis.  Sie können die SYS\-Headerdateien Stelle platzieren, wenn Sie nicht beabsichtigen, die Programme dem UNIX\- zu transportieren.  
  
-   Verwenden Sie das UNIX\-kompatible Pfadtrennzeichen in den die Routinen, die Zeichenfolgen verwenden, die Pfade und Dateinamen als Argumente darstellen.  UNIX unterstützt nur den Schrägstrich \(\/\) zu diesem Zweck Win32\-Betriebssysteme während den umgekehrten Schrägstrich \(\\\) und den Schrägstrich unterstützen \(\/\).  Folglich verwendet diese Dokumentation UNIX\-kompatible Schrägstriche als Pfadtrennzeichen in `#include`\-Anweisungen, z. B \(jedoch, unterstützt die Windows\-Betriebssystembefehlsshell, CMD.EXE, den Schrägstrich in Befehlen, die an der Eingabeaufforderung eingegeben werden\).  
  
-   Verwenden Sie Pfade und Dateinamen, die ordnungsgemäß in UNIX arbeiten, das die Groß\-\/Kleinschreibung beachtet wird.  Das Dateizuordnungstabellen \(fat\)\- Dateisystem in Win32\-Betriebssystemen wird Groß\-\/Kleinschreibung nicht beachtet; der NTFS\-Dateisystem\-Konservenkasten für Verzeichnislisten jedoch ignoriert Fall in den Dateisuchen und anderen Systemvorgängen.  
  
    > [!NOTE]
    >  In dieser Version von Visual C\+\+, sind UNIX\-Kompatibilitätsinformationen von den Funktionsbeschreibungen entfernt.  
  
## Siehe auch  
 [Kompatibilität](../c-runtime-library/compatibility.md)