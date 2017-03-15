---
title: "H&#228;ufig auftretende 64-Bit-Migrationsprobleme bei Visual C++"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Portieren von 32-Bit-Code [C++]"
  - "64-Bit-Anwendungen [C++]"
  - "64-Bit-Compiler [C++], Migration"
  - "64-Bit-Compiler [C++], Portieren von 32-Bit-Code"
  - "64-Bit-Programmierung [C++], Migration"
  - "Migration [C++], Probleme bei 64-Bit-Code"
  - "Portieren von 32-Bit-Code auf 64-Bit-Code"
  - "Aktualisieren von Visual C++-Anwendungen, 32-Bit-Code"
  - "Win64 [C++]"
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
caps.latest.revision: 19
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# H&#228;ufig auftretende 64-Bit-Migrationsprobleme bei Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mit Visual C\+\+ Anwendungen erstellen, die unter einem 64\-Bit\-Windows\-Betriebssystem ausgeführt werden sollen, sollten Sie folgende Probleme berücksichtigen:  
  
-   `int` und `long` sind unter 64\-Bit\-Windows\-Betriebssystemen 32\-Bit\-Werte.  Bei Programmen, die Sie für 64\-Bit\-Plattformen kompilieren möchten, sollten Sie darauf achten, keine Zeiger auf 32\-Bit\-Variablen zuzuweisen.  Zeiger sind auf 64\-Bit\-Plattformen 64\-Bit\-Werte, und der Zeigerwert wird abgeschnitten, wenn Sie sie einer 32\-Bit\-Variable zuweisen.  
  
-   `size_t`, `time_t` und  `ptrdiff_t` sind unter 64\-Bit\-Windows\-Betriebssystemen 64\-Bit\-Werte.  
  
-   `time_t` ist unter 32\-Bit\-Windows\-Betriebssystemen in Visual C\+\+\-Versionen vor Visual C\+\+ 2005 ein 32\-Bit\-Wert.  `time_t` ist jetzt standardmäßig eine 64\-Bit\-Ganzzahl.  Weitere Informationen finden Sie unter [Time Management \(auf Englisch\)](../c-runtime-library/time-management.md).  
  
     Sie müssen berücksichtigen, wo der Code einen `int`\-Wert nimmt und als einen `size_t`\- oder `time_t`\-Wert verarbeitet.  Die Zahl kann unter Umständen größer als eine 32\-Bit\-Zahl werden, und Daten werden abgeschnitten, wenn sie wieder an den `int`\-Speicher übergeben werden.  
  
 Der %x\-Modifzierer\(Hexadezimal\-`int`\-Format\) `printf` funktioniert unter einem 64\-Bit\-Windows\-Betriebssystem nicht wie erwartet.  Er funktioniert nur auf den ersten 32 Bits des Werts, der an ihn übergeben wird.  
  
-   Verwenden Sie %I32x, um einen 32\-Bit\-Ganzzahltyp im Hexadezimalformat anzuzeigen.  
  
-   Verwenden Sie %I64x, um einen 64\-Bit\-Ganzzahltyp im Hexadezimalformat anzuzeigen.  
  
-   %p \(Hexadezimalformat für einen Zeiger\) funktioniert unter einem 64\-Bit\-Windows\-Betriebssystem wie erwartet.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Compileroptionen](../build/reference/compiler-options.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="8228b16e9fef41dbba1af1d78bf0cc87" class\="tgtSentence"\>Tipps zur Migration\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## Siehe auch  
 [Konfigurieren von Programmen für 64\-Bit](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [Portieren des Programms](assetId:///c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)