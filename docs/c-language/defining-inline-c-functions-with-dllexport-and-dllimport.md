---
title: "Definieren von C-Inlinefunktionen mit dllexport und dllimport"
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
  - "C"
helpviewer_keywords: 
  - "dllexport-Attribut [C++]"
  - "dllexport-Attribut [C++], Inlinefunktionen"
  - "dllimport-Attribut [C++], Inlinefunktionen"
  - "Inlinefunktionen [C++], Mit dllexport und dllimport"
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Definieren von C-Inlinefunktionen mit dllexport und dllimport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Sie können eine Funktion mit dem `dllexport`\-Attribut als inline definieren.  In diesem Fall wird die Funktion immer instanziiert und exportiert, unabhängig davon, ob ein beliebiges Modul im Programm auf die Funktion verweist oder nicht.  Die Funktion wurde vermutlich von einem anderen Programm importiert.  
  
 Sie können auch eine Funktion als inline definieren, die mit dem **dllimport**\-Attribut deklariert wurde.  In diesem Fall kann die Funktion \(gemäß der Compileroption\-Spezifikation "\/Ob \(inline\)"\) erweitert, aber niemals instanziiert werden.  Insbesondere bei Verwendung der Adresse der inline\-importierten Funktion wird die Adresse der Funktion in der DLL zurückgegeben.  Dieses Verhalten stimmt mit der Übernahme der Adresse einer nicht\-inline importierten Funktion überein.  
  
 Statische lokale Daten und Zeichenfolgen in Inlinefunktionen behalten die gleichen Identitäten zwischen der DLL und dem Client wie in einem einzelnen Programm \(d. h. eine ausführbare Datei ohne DLL\-Schnittstelle\) bei.  
  
 Lassen Sie beim Bereitstellen von importierten Inlinefunktionen Sorgfalt walten.  Gehen Sie beispielsweise beim Aktualisieren der DLL nicht davon aus, dass der Client die geänderte Version der DLL verwendet.  Um sicherzustellen, dass Sie die richtige Version der DLL laden, erstellen Sie auch den DLL\-Client neu.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Import\- und Exportfunktionen einer DLL](../c-language/dll-import-and-export-functions.md)